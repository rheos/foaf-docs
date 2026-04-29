# Radix Roadmap

This roadmap scopes the work to bring FOAF onto Radix and stand up the on-chain layers that follow. It's a technical sequence rather than a calendar — dates remain volatile until the bridge work begins in earnest. Most milestones are gated by the previous one shipping, not by a fixed quarter.

The main Foundation roadmap (`technical/roadmap.md`) covers GrowOperative, the marketplace, and Foundation operations. This document covers Radix specifically. The two are layered: items here will be referenced in the main roadmap at the milestone level once dates firm up, and detailed scope continues to live here.

---

## Bridge Deployment

Get FOAF onto Radix Babylon via Hyperlane. This is the prerequisite for everything else.

What ships:
- Scrypto resource for FOAF on Radix Babylon (fungible, fixed supply matching Ethereum, divisibility chosen to match ERC-20 convention, metadata configured)
- Hyperlane warp route configuration between Ethereum and Radix with FOAF as the bridged asset (lockbox or burn-and-mint, ISM choice spelled out and justified)
- Testnet round-trip validated end-to-end before mainnet deploy

Detailed scope: [radix-bridge.md](./radix-bridge.md).

What this unlocks:
- FOAF is transferable on Radix and can be the asset of a Radix-native sale
- Foundation can hold native Radix-side FOAF in its treasury
- Future Scrypto components (staking, governance, RHEO emission) have something to integrate against

Status: scoped, not staffed. Looking for a developer with Scrypto + Hyperlane experience.

---

## Radix-Native FOAF Sale and Validator Deployment

Once the bridge is live, run a Radix-native FOAF token sale paying in XRD. Use the proceeds to deploy a Foundation-run Radix validator.

What ships:
- Sale mechanism on Radix (DEX listing, sale platform, or direct foundation issuance — decision pending)
- Sale terms with jurisdictional gating (no US retail), KYC where required, foundation-side fulfillment
- Foundation Radix validator running with self-stake at a credible position in the active validator set
- Owner LSU lock applied (28-day unstaking delay) as commitment signal
- Liquid XRD reserve sized for ~4-5 months of foundation on-chain operations to absorb the unstaking delay

Allocation: drawn from the Seed Round bucket (40% / 10M FOAF), specifically positioned alongside Seed 2 (5M international) rather than as a separate allocation. Exact size depends on FOAF/XRD pricing decisions and the target self-stake size.

Why this order:
- Bridge has to ship first or there's nothing to sell on Radix
- Sale audience and validator delegation audience are the same people (Radix-natives), so the sale builds the delegator pool too
- Validator self-stake from sale proceeds keeps the foundation independent of community delegation as a credibility prerequisite

What this unlocks:
- Radix-native FOAF distribution to the audience that will use it on Radix
- Validator revenue (Radix staking APY ~9-12% plus commission on delegated stake) offsets node-running ops
- XRD treasury position for ongoing foundation-layer gas
- Reputation as a Radix ecosystem participant rather than just a future deployer

---

## DAO, Staking, and RHEO Emission

Deploy the on-chain governance and economic layer. This is where vFOAF/rFOAF staking, RHEO generation, and DAO governance contracts go live.

What ships:
- vFOAF and rFOAF staking contracts (lock mechanics, time-lock multipliers, non-transferable resource semantics)
- RHEO emission curves (FOAF-staked-to-RHEO-per-epoch math, with multiplier curves likely needing the scrypto-math exp/log library)
- Governance contracts: threshold-tiered voting (Tier 0 signaling through Tier 4 constitutional), badge-gated council actions
- Treasury management contracts for foundation operations on chain

What this unlocks:
- FOAF holders can stake productively on Radix
- DAO decisions can be made on chain instead of through informal foundation control
- RHEO becomes available to back transactions for users in trust graphs that include stakers
- The protocol economic layer the rest of the application depends on

Coordination with the main roadmap: this is what the pitch doc calls "Phase 3 Radix Babylon deployment" and "vFOAF and rFOAF staking goes live."

---

## Custodial Wallet System for Five Free FOAF

Build the onboarding infrastructure that lets non-crypto users participate. Verified new users receive 5 vFOAF through a custodial wallet — no seed phrases, no gas, no crypto literacy required.

What ships:
- Custodial wallet service with signing-on-behalf-of-user semantics
- KYC / identity verification (matching the "verified new user" requirement of the airdrop)
- Distribution mechanism that mints/transfers 5 vFOAF on signup
- Eventual self-custody migration path (user can graduate from custodial to their own wallet if they want)

Why this order:
- Sale audience self-serves with their own wallets and doesn't need this
- Custodial wallets are real product engineering — design, custody, security, recovery, support — and the foundation needs the runway from the sale to fund this work
- The audience this serves (GrowOperative end users in Crawford Bay, Kaslo, future communities) is the audience the protocol exists for; the custodial layer is what brings them on chain without making them learn crypto

What this unlocks:
- Mass-market onboarding to the FOAF protocol
- The Five Free FOAF airdrop running at the scale the tokenomics intends
- A growing base of FOAF-holding network members who can extend credit, vote at signaling tiers, and use RHEO without ever managing keys

---

## User-Side RHEO Transactions On Chain

The point at which user trades, settlement, and credit operations actually move on chain. Until this milestone, GrowOperative continues to run on Rails with FOAF as the off-chain authoritative ledger.

What needs to be true before this is safe to ship:
- Custodial wallet system stable at production scale
- DAO/staking/RHEO emission running cleanly
- Validator and on-chain operational costs predictable and funded
- Trustline credit graph contracts on Radix tested end-to-end with real flows
- Path forward decided for the FOAF-authoritative cutover (see project memory on this)

This is Phase 4 territory in the pitch doc framing. It's the milestone where the protocol becomes the source of truth for credit, not just the eventual settlement layer beneath it.

What this unlocks:
- Cross-subnet credit clearing
- On-chain proof for trustlines that opt in
- The architecture the protocol was always heading toward

---

## Notes

- **Dates omitted intentionally.** Bridge deployment timeline alone could swing weeks based on developer availability. Sale timing depends on bridge plus sale infrastructure plus jurisdictional setup. Custodial wallet engineering is multi-month. Pinning quarter-by-quarter dates before the bridge starts shipping invites missed-milestone optics. Sequence is firmer than dates.
- **Coordination with main roadmap.** Once each milestone has a credible date, it surfaces in `technical/roadmap.md` at the line-item level. The main roadmap shouldn't go silent on Radix while this work happens — at minimum, the sequence should be visible there even before exact dates land.
- **This roadmap is technical scope.** Investor narrative, fundraising milestones, and partnership timelines are tracked separately and shouldn't be conflated with what gets built on Radix.
