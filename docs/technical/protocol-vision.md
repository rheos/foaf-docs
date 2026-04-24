# Protocol Vision: Peer-to-Peer, Private, Open

This document describes the long-term architectural direction for FOAF — where the protocol is headed as the ecosystem matures beyond its current centralized reference implementation. It complements the [current architecture](./architecture.md) and the [technical roadmap](./roadmap.md).

The short version: **FOAF is an open protocol with an open source reference client, not a SaaS product.** The long-term target is a peer-to-peer, trust-graph-routed, content-private system where any community, co-op, or business can run a node — with no mandatory central operator.

---

## The vision in one paragraph

Item listings and requests propagate from device to device along trustline edges using gossip — each viewer sees prices composed along the path that reaches them. Trustline state (credit, balances, payments) lives bilaterally on the two counterparty devices, not on a central server. The central database shrinks to opaque content hashes and supply-chain status pointers — operators cannot enumerate what is being traded. Offline transactions between two parties work over Bluetooth, NFC, or mesh. Cryptography is invisible to the user — keys hide behind ordinary mental models like contacts, accounts, and trusted friends. Optional blockchain anchoring provides tamper-evidence without moving private data on-chain. Any community, co-op, or business can run a node or use a federated relay.

---

## Why this architecture fits

Most "decentralized private" ambitions founder on problems that don't exist in FOAF's domain:

- **No global consensus problem.** Mutual credit is inherently bilateral. The hardest problem other decentralized systems face — everyone agreeing on a single ledger of money — doesn't apply. Credit lives between two parties.
- **The trust graph *is* the routing topology.** Peer discovery is free — trustline edges already define who talks to whom.
- **Community scoping replaces planetary consensus.** Each community can run its own relays. The protocol needs neighborhood-scale gossip, not planet-scale agreement.
- **Items are inherently local** (food, labor, services). Latency across continents doesn't matter. The physics of the product match the architecture.
- **Users physically meet to trade.** QR-code-on-first-meet solves identity verification naturally — the social verification has already happened in person.

---

## Three layers

The system is built in three logical layers, each with pluggable implementations.

### FOAF — the skeleton

Owns everything that needs bilateral agreement:
- Trust graph edges (who trusts whom, for how much)
- Bilateral credit state and settlement protocol
- Pending operations (reservations, commitments, pending payments)
- Supply-chain status transitions

### Gossip — the body

Carries everything informational:
- Item listings (content-addressed by seller-signed hash)
- Requests and discovery
- Price composition along trust paths

Stale data is just stale; no consensus needed.

### Central infrastructure — shrinks dramatically

Retained only for:
- Opaque content hashes pointing to items
- Supply-chain status events
- User directory and identity anchors
- Optional federated relays

Operators see hashes and routing metadata, never content. In a federated deployment, "the operator" is whoever the community has chosen to run their relay — not a platform vendor.

---

## Privacy, layered

Privacy comes in phases, from easy wins to advanced cryptography.

1. **Bilateral state off the central server.** Trustline balances live only on the two counterparties' devices, synchronized device-to-device. Operators cannot see any user's balances. This alone captures the large majority of the privacy value with no exotic cryptography.
2. **Onion-routed multi-hop payments.** When a payment needs to travel through intermediaries, each hop sees only "forward this to my next neighbor" — not the payment's origin or destination. Lightning Network's approach, applied to credit.
3. **Confidential amounts (optional).** Even hide transaction amounts from peer observers using zero-knowledge proofs. Deferred until explicitly needed; adds real engineering cost.

At Layers 1 and 2 you can honestly say: operators cannot enumerate what is being traded; operators cannot see balances; multi-hop intermediaries cannot see endpoints.

---

## The user experience principle: crypto is invisible

Target users are community traders — gardeners, co-op members, small producers — not crypto enthusiasts. The whole architecture collapses if the user experience asks them to understand cryptography.

**Core rule: no crypto terminology in the user interface, ever.** No "public key," "signature," "hash," "handshake." Only human concepts: account, contact, verified, trusted friends, backed up.

What's actually happening | What the user sees
--- | ---
Generate identity keypair on first launch | "Welcome! Pick a username."
Encrypted device Keychain backup | "Your account is saved."
Scan QR to exchange keys and handshake | "Scan to add Alice as a contact" — *bleep* — "Alice added"
Social recovery via guardians | "Pick 3 friends who can help you get your account back"

The load-bearing insight: **users already have real-world trust relationships**. Bob knows Alice from the farmer's market. Social verification has already happened in person. FOAF's job is to capture these existing relationships, not to bootstrap trust from scratch. That's why the system doesn't need the zero-trust machinery Bitcoin does.

---

## Recovery: multiple independent backups

Account recovery stacks several independent mechanisms so any one is sufficient:

1. **Cloud backup via platform keychain.** iCloud Keychain or Google Credential Manager, end-to-end encrypted. Default-on for most users; invisible until needed.
2. **Social recovery via the trust graph.** User picks 3+ trusted contacts; 2 can collectively authorize a new device. The trust graph provides the social infrastructure for free.
3. **Counterparty re-sync.** Because trustline state is bilateral, each counterparty holds a copy of the relationship. Even with zero other backup, a user can reinstall, generate a fresh key, contact their counterparties, and re-bind the trustlines.
4. **Recovery phrase (opt-in, advanced).** For users who want full self-sovereignty, not the default path.

---

## Peer addressing

Identity is a public key. Addressing is a list of relays the user chooses to receive messages through. IP addresses are an implementation detail the protocol never exposes.

- **Identity = public key.** Alice's identity is her long-term keypair.
- **Address = Alice's chosen relays.** She tells the world "I'm reachable via `relay.cooperative.coop` and `community-relay.farmnet.org`." Messages for her are posted to those relays; her devices subscribe and pick them up when online.
- **Mobile-friendly.** Devices connect outward to relays, so NAT and changing IPs don't matter. Multiple devices subscribe to the same mailbox.
- **Offline-friendly.** Relays hold messages until the user's device is online.
- **User-switchable.** Alice can change relays any time; she publishes a signed relay-update event and her contacts update automatically. No lock-in.

Contact exchange is **one-sided** — one person scans the other's QR code (which carries pubkey + relay list + signed attestation), then the other confirms the incoming request. Physical proximity is the verification channel; mutual scanning would double the friction with no cryptographic benefit. For remote connections, invite links carry the same payload. For friend-of-friend connections, a mutual contact's signed attestation substitutes for in-person scanning.

---

## Relay infrastructure

Relays are necessary — phones sleep, move networks, and aren't reliably reachable from the public internet. Something has to hold messages for a user until their device is online. But **necessary doesn't mean centralized.**

The model is federated, same as email, Matrix, or Nostr:

- **Many relays, run by many operators** — communities, co-ops, self-hosters, commercial services, the foundation
- **Users choose which relay(s) to use** and can switch any time
- **Relays interoperate** — the protocol specifies how, not a vendor
- **Relays are dumb mailboxes, not authorities.** They hold encrypted messages for subscribers. They don't authenticate trustline state, don't see message content, don't mediate trades. If a relay disappears, users switch to another; identity, history, and counterparties are untouched.

**Who runs them:**

- A community co-op runs one for its members (like running a community Mastodon instance)
- A subnet operator includes a relay as part of onboarding
- A technically savvy user self-hosts a small relay for themselves, family, and close friends
- A commercial service offers paid relay hosting for users who want someone else to run it
- The FOAF Foundation runs reference relays for continuity — not mandatory to use

**Cost to run one:** a few dollars per month of hosting for a community of dozens, tens of dollars for hundreds. Operational skill at "set up a Mastodon instance" level.

The mental model is email. Email needs servers. Someone runs them. But no single server is mandatory, users can switch providers, federation works, the protocol outlives any individual server. That's the shape.

---

## Transport: layered connectivity

The protocol doesn't care how signed messages travel. The client can fall through a stack of transports based on what's available:

1. **Internet** (default, fastest)
2. **LAN / WiFi-Direct** (co-located devices without internet)
3. **Bluetooth proximity** (farmer's markets, pickups, nearby devices)
4. **LoRa mesh** (long-range low-bandwidth; community backbone for rural areas)
5. **Store-and-forward** (any device ferries messages between transports)

Mesh is treated as augmentation, never the primary transport. Prior phone-only mesh attempts (like FireChat in 2014) struggled because they relied on strangers to relay messages with no incentive, on phones that sleep and drain batteries, in chaotic RF environments. FOAF's structure avoids all of this: relay happens between trust-connected peers who have social incentive; dedicated LoRa hardware beats phone-only meshes; transaction data is small and delay-tolerant, perfect for lossy transports.

The real-world payoff: a farming community can deploy a handful of LoRa nodes as a backbone, and trades work across the whole community regardless of cell coverage.

---

## Scale-continuous, not scale-bifurcated

Community garden sharing is GrowOperative's root and stays its root. The architecture is built so the same protocol and reference client serve a backyard gardener sharing zucchini *and* a regional food distributor managing commercial farm-to-table supply — without bifurcating the product into "community" and "enterprise" tiers.

### Why it works structurally

- **Trustlines are trustlines at any scale.** $0 neighborhood sharing and $5M commercial invoices use the same primitive. The protocol doesn't care about magnitude.
- **Subnets are the scaling mechanism.** Garden subnets and farm-to-table subnets coexist in one network, with different policy configurations but the same underlying protocol.
- **Advanced features benefit small users too.** Chain-anchored organic claims matter as much to a backyard gardener as to a certified farm. Same feature, different stakes.

### What this rules out

- No "Pro" or "Enterprise" tier — features are universal, configurations differ
- No separate app SKUs — one reference client, one codebase
- No divergent UX — scale adds density, not complexity
- No protocol-level fees that scale with revenue — relay operators can charge for services, but the protocol itself takes no platform cut
- Free $0 trades stay first-class citizens

### The gut check

A neighbor sharing cucumbers and a food co-op settling $50K of invoices should both experience the system as "the app." Same primitives, same gestures, same feel. Scale is additive, never replacement.

This principle works alongside the protocol-first commitment: because there's no central operator, there's nobody to extract a commercial-tier cut; because the protocol is uniform, there's nothing to gate behind a tier; because subnets are user-configured, communities own their own complexity.

---

## Optional blockchain verifiability

Pure bilateral peer-to-peer doesn't require a blockchain, but chain integration adds value in three specific places:

1. **Anchoring.** Periodic cryptographic commitments of FOAF state posted to a public chain make bilateral state tamper-evident — even against a malicious counterparty. Private data stays off-chain; only a hash goes on.
2. **Optional on-chain settlement.** For high-value trades that need full on-chain proof, move that specific trustline to an actual on-chain implementation (Trustlines Protocol on Gnosis, or the equivalent on Radix). The protocol's API surface is already compatible. Everyday community trades stay off-chain and free.
3. **Auditor / regulator access.** Zero-knowledge proofs against anchored state let a business prove compliance (e.g., "our trade credit never exceeded $X this quarter") without revealing any individual transaction.

Chain integration stays optional. The default path is pure peer-to-peer for privacy, cost, and simplicity.

---

## Protocol-first, not product-first

This is the load-bearing strategic commitment.

FOAF is not "a company that sells a platform with an enterprise tier." It's **a protocol with a reference client**, closer in shape to email, Matrix, Lightning Network, or Nostr than to Salesforce or Stripe.

What this means concretely:

- **The GrowOperative app becomes the reference client**, not the platform. Other clients can exist; anyone can fork or build from the spec.
- **Any business can run its own node** or use a federated relay provided by a community, co-op, or commercial service. No vendor lock-in.
- **Compliance is a client-side concern.** The protocol emits signed, verifiable event logs. Accountants, auditors, and tax authorities already know how to work with ledgers of signed events.
- **Dispute resolution is protocol + legal system.** Signed bilateral contracts have legal standing regardless of the underlying technology.
- **Governance is explicit.** Protocol changes go through a documented, community-reviewed, versioned proposal process (in the tradition of Bitcoin's BIPs or Ethereum's EIPs).

### Scale arc

Community-scale is the first deployment of a protocol that anyone can adopt. The ecosystem widens outward as adoption grows:

- Food co-ops and regional farm networks
- Craft and maker economies
- Developing-market trade credit, where banking is thin and trade credit is everything
- Supply chain financing, where multilateral netting can unlock substantial working capital
- Cooperative networks whose existing values already match the architecture

Each new adopter brings their own node, their own clients, their own compliance stack. The protocol stays invariant; the ecosystem composes around it.

### Why the architecture is already aligned

- **API surface is Trustlines-Protocol-compatible**, so Gnosis deployment is a latent option, not a rewrite
- **The `protocol/` boundary in the current codebase is Radix/Scrypto-portable**, so on-chain deployment is a latent option
- **Bilateral trustlines** mirror Lightning's protocol-first shape

These seams were drawn in the right places from the start.

---

## Honest caveats

- **"Fully decentralized" is a spectrum.** Realistic systems end up hybrid. The goal is *no mandatory central operator*, not "no operators at all."
- **This is a multi-year program.** Each migration phase is significant engineering; each phase is independently valuable. Ship in order of value-per-effort.
- **Governance is hard and must be designed from the start.** Retrofitting governance onto an open protocol is painful.
- **Funding long-term maintenance is the real challenge.** Open protocols survive via foundations, grants, and service businesses — not subscription revenue.
- **Mobile peer-to-peer has real constraints** (battery, background networking, OS restrictions). Expect community-scoped relays to handle continuous availability.

---

## Related reading

- [Current technical architecture](./architecture.md)
- [Technical roadmap](./roadmap.md)
- [Decentralization roadmap](../growoperative/decentralization-roadmap.md)
- [FOAF Marketplace vision](../foaf-marketplace/vision.md)
- [Foundation governance](../foaf-foundation/governance.md)
