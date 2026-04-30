# FOAF Design Principles

This document captures load-bearing design principles that shape FOAF/GrowOperative's architecture and product decisions. These are decided positions, not exploratory notes — when they conflict with implementation choices, the principle wins and the implementation gets revisited.

## No cash paywall on participation in a cash-alternative system

**The principle:** No cash subscription, no paywall, no fiat fee required for users to participate in FOAF/GrowOperative.

**Articulation:** I don't want people to have to pay cash to use a system whose purpose is to avoid spending cash.

**Why this matters:**

This is the structural difference between FOAF and centralized comparables (Credex/Great Sun, BarterPay/Barter It). Each of those projects asks users for fiat cash (monthly subscription) to participate in a cash-alternative system. That's a contradiction at the design level — the cash-alternative is paywalled by cash.

FOAF's foundation-issued, token-funded, DAO-governed model resolves this contradiction by:

- No subscription required to use the network
- Five Free FOAF airdrop gives new users vFOAF without payment
- Phase 1 zero protocol fees (DAO-governed; fees activate later but paid by transaction-profit-takers, not by participants for participating)
- Foundation operations funded by token economics, not by user subscription extraction

**Why this is the price of the legal/financial complexity:**

Subscription revenue (Credex's model) is the simpler path. Securities law isn't an obstacle for SaaS subscriptions; it's only an obstacle when funding operations through token sales. So FOAF accepts the harder path (Dubai DIFC, no-US-retail, careful copy framing, token mechanics) specifically to avoid the cash-paywall failure mode.

The complexity isn't an idealistic accident. It's the necessary cost of structurally aligning the funding model with the mission.

**Implications for design and copy:**

- Any mechanism that requires users to pay fiat for access to participate in the network is incompatible with this principle. Subscription tiers, paywalled features, fiat fees on participation — all rejected.
- Compatible funding models: token economics, foundation issuance, transaction fees on profit-takers, grants.
- When comparing FOAF to projects with subscription models (Credex, BarterIt, etc.), this principle is the load-bearing differentiator.
- FOAF should never describe itself in ways that could imply "subscribe to participate" or "pay to access the network." The free-to-participate framing is structural, not promotional.

## Public option for trade infrastructure — P2P-first, scaling up to any volume

**The principle:** GrowOperative starts at the peer-to-peer community scale — neighbours sharing surplus, gardeners trading produce, individuals with skills and time — and scales upward toward larger commercial use without abandoning the community foundation. Universal access at every scale. The protocol is a public option for trade infrastructure, available to anyone regardless of size, geography, or wealth.

**Distinguished from WIR / Sardex:**

WIR Bank (Switzerland, since 1934) and Sardex (Sardinia, since 2010) are the canonical precedents for mutual credit working at scale over time. Both started B2B regional and stayed B2B regional. They didn't try to expand into consumer markets or cross-border use. That's a coherent strategic choice, and it's why they're durable — but it's not what FOAF is going for.

FOAF is going the other direction: start at the consumer/P2P scale and architect for scaling up to large-volume B2B and potentially cross-border use, on the same protocol. Same primitives, same client, same UX, different scales of participation.

**Why P2P-first scaling up has structural advantages:**

- **Inclusivity becomes load-bearing from day one.** A system that starts with backyard gardeners sharing zucchini can only add B2B by keeping the gardener experience first-class. A system that starts B2B-only and tries to add consumer access later usually creates tier systems that gradually marginalize the consumer side.
- **The "public option" framing is genuine, not retrofitted.** WIR and Sardex are private B2B networks that members join. FOAF as universal infrastructure is a different positioning — closer to email or the postal service than to a business club.
- **Network effects compound across scales.** A backyard gardener using the same protocol as a farm-to-table supplier means they can transact with each other. A B2B-only network can't easily absorb consumer flows when they arrive.
- **Cross-border ambition fits the architecture.** P2P consumer-scale credit infrastructure that works for someone in Crawford Bay also works for someone in Lebanon, Argentina, or Zimbabwe. Geographic openness is a property the architecture has from day one rather than something to be retrofitted.

**Why "public option" framing matters:**

The term comes from a healthcare context — a public option is a service available to everyone on equal terms, sustainably funded, coexisting with private alternatives, not extractively monetized. Applied to trade infrastructure, it means:

- Universal access at every scale — backyard gardener and regional distributor on the same protocol
- Sustainable foundation funding (token economics, grants, service-business income) rather than user-extractive monetization
- Coexists with private alternatives (BarterPay, banks, Credex, cash) without trying to be the only option
- Doesn't gate participation by size, wealth, or commercial sophistication
- Operator-neutral — anyone can run a node, no mandatory central operator

**Implications for design and copy:**

- The protocol and reference client must work at $0-trade neighbourhood scale AND at large-volume commercial scale on the same primitives. Scale-continuous, not scale-bifurcated.
- No "Pro" tier, no enterprise-only features, no commercial-rate-limiting on community use.
- When fees activate (Phase 3 onward, DAO-governed), they cannot gate basic participation — only profit-taking transactions.
- Onboarding stays accessible as commercial users join. New consumer users should never be made to feel like the system has moved on without them.
- Cross-border deployment is a goal, not a constraint to be managed. The architecture shouldn't assume Canadian context.
- Copy framing: GrowOperative is infrastructure available to everyone, not a service some people pay for. The cooperative-governance direction reinforces this.

**Coordination with other commitments:**

This principle interlocks with several others already in motion:

- **No cash paywall on participation** (above) — universal access requires no fiat barrier to entry.
- **Scale-continuous, not scale-bifurcated** (per `Growoperative/docs/claude/v2-p2p-vision.md`) — the architectural mechanism that makes universal scale-up possible.
- **Cooperative governance** (per foaf-tokenomics) — operational capacity scales with FOAF held; governance weight does not. Members govern as members, not as customers paying for tiers.
- **Protocol-first, not product-first** (per v2-p2p-vision.md) — the protocol survives any single operator, including the foundation itself eventually.

## FOAF is infrastructure; apps are the ecosystem

**The principle:** FOAF provides shared foundational infrastructure used by many apps. Apps built on top can have any business model — free, co-op, SaaS, commercial, niche-specialist, regional, B2B-only, whatever fits the use case. The infrastructure stays public-option; the ecosystem on top is diverse.

This is the same layering pattern that lets email coexist with Gmail (SaaS), ProtonMail (paid privacy), Apple Mail (bundled), Postfix (self-hosted), Mailchimp (commercial), and a thousand niche services. SMTP/IMAP is the public commons; the apps are the ecosystem.

**What lives in the shared infrastructure layer:**

- **Authentication and identity.** One identity per user, usable across every app in the ecosystem.
- **Credit lines (trustlines).** A user's bilateral trust relationships are theirs across all apps. Robin's trustline with his neighbour exists once, used by every app the relationship is relevant to.
- **Social graph.** The trust topology — who knows whom, who's willing to extend credit to whom — is shared across apps, not re-discovered per app.
- **Subnets.** Community-scoped onboarding and policy configuration is at the protocol level. A subnet is a set of users with shared norms, usable by any app whose use case fits.
- **Supply chain management primitives.** Reservations, commitments, multi-hop pending-ops, fulfillment status — the protocol primitives that GrowOperative uses for food are reusable for any goods-or-services workflow.
- **Routing and credit loops.** Multi-hop pathfinding, atomic settlement across hops, credit-loop discovery and cancellation. Any app that does mutual credit gets these for free.
- **Optional on-chain primitives.** FOAF token, RHEO emission, governance contracts, treasury, anchored settlement — same on-chain stack serves whatever app integrates it.

**What lives in the app layer:**

- UI and UX for a specific use case (food sharing, skill/labor exchange, tool libraries, local services, B2B supply chains, childcare swaps, etc.)
- Vertical-specific data (item catalogs, request flows, fulfillment workflows, search, discovery)
- App-specific business model (free, donation-funded, subscription, transaction fees, sponsored, etc.)
- App-specific governance (the foundation governs the protocol; individual apps can be governed however their operator chooses)
- App-specific branding, audience, geography, regulatory posture

**Why this layering matters:**

- **Network effects compound across apps.** A user who joins the ecosystem through GrowOperative for food can use a future skill-exchange app without re-creating their identity, social graph, or credit relationships. Every additional app increases the value of being in the ecosystem.
- **Diverse business models are healthy.** Apps with different funding strategies (free community apps, SaaS for commercial users, niche services) make the ecosystem resilient. The same protocol can support a public-option food-sharing app and a paid B2B supply-chain SaaS without contradiction.
- **The infrastructure stays a commons even as commercial apps thrive on top.** This is what "public option" actually means in this context: not "everything is free forever," but "the underlying coordination layer is free and open, and people can build whatever services they want on top of it."
- **Operator-neutral by design.** No single app operator controls the ecosystem. If one app fails or gets acquired or pivots away, users keep their identity, relationships, and credit lines, and can move to alternative apps without losing anything important.

**Clarifications about the existing principles:**

The earlier principles (no cash paywall, public option) apply specifically to the FOAF infrastructure layer, not to apps built on top.

- An app charging a subscription for its own UX doesn't violate the no-cash-paywall principle, as long as users can access the underlying FOAF protocol without paying that app's subscription. They could use a different app or self-host or use a community-run free alternative.
- An app being commercial SaaS doesn't violate the public-option principle, as long as the underlying infrastructure remains universally accessible and the user retains their identity/credit/social graph independently of any specific app.

The line is between **infrastructure** (foundation-stewarded, universally accessible, no paywall) and **apps** (operator-stewarded, business-model-of-their-choice, ecosystem participants).

**What this rules out:**

- Foundation-issued apps that paywall participation in the FOAF protocol itself (would violate no-cash-paywall).
- Apps that capture user identity, credit, or social graph in app-specific data structures rather than in the shared protocol layer (would violate the layering and create app lock-in).
- Vertical-specific protocol changes that benefit one app at the expense of another (the protocol stays universal; vertical concerns live in the app layer).
- Apps that are bundled with the foundation in a way that suggests they're part of the protocol (would create confusion about what's public infrastructure vs. what's a service).

**Implications for design and copy:**

- Treat each foundational layer (auth, credit lines, social graph, subnets, supply chain primitives) as a shared resource owned by the protocol, not by GrowOperative or any specific app.
- When designing new functionality, ask: "Is this infrastructure (shared by all apps) or app-specific (one vertical's concern)?" The answer determines where it lives and how it gets governed.
- The foundation governs the infrastructure. Individual apps choose their own governance, terms, and business model within the constraints of the protocol.
- GrowOperative is one app in the ecosystem. It happens to be the first and the reference, but the framing should be "an app on FOAF" not "the FOAF app."
- When pitching the project, distinguish carefully between FOAF (the protocol/infrastructure) and GrowOperative (the first app). Conflating them obscures the ecosystem story and makes the project look like a single product rather than infrastructure-plus-app.

**Coordination with existing memory:**

The trustline-system-is-multi-app memory entry already captures part of this — trustlines are shared infrastructure, not GrowOperative-specific. This principle generalizes that observation to the full foundational layer (auth, credit lines, social graph, subnets, supply chain). Future apps inherit all of these, not just trustlines.
