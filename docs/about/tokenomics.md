# FOAF Foundation tokenomics

The FOAF Foundation supports community-scale trade and resilience through a dual-token system designed for utility rather than speculation. This document describes how those tokens are structured, how they relate to each other, and how the FOAF Foundation intends to distribute them.

## Token history and legitimacy

The FOAF token is not a new launch. The contract was deployed to Ethereum mainnet in December 2018 at address [`0x51300E946bcd4850Db3bE28D1FcC4076Ba4a9288`](https://etherscan.io/token/0x51300E946bcd4850Db3bE28D1FcC4076Ba4a9288). Total supply is 25 million, indivisible, fixed, and has never been distributed. The Foundation holds the entire allocation.

This 7-year on-chain history is meaningful in two ways. It establishes the token as something other than a recent issuance, and it gives the Foundation a clean slate to design a distribution mechanism that meets present-day legal and operational standards rather than inheriting any prior commitments.

The system uses two tokens with separated roles:

- FOAF: a fixed-supply governance and staking token, existing on Ethereum since 2018, bridged to Radix in Phase 3.
- RHEO: a flexible-use utility token consumed by network operations and generated through FOAF staking.

This document describes how both tokens support GrowOperative and the broader FOAF ecosystem, with a multi-location soft launch underway in Crawford Bay, BC, and expansion through other Kootenays communities (Kaslo, Nelson) planned for 2026.

---

## How it works

GrowOperative helps people trade food, goods, and services with or without cash. Listings are priced in local currency (e.g., $2 CAD per pound of tomatoes), and trades can settle in:

- Cash, broadly defined: e-Transfer, PayPal, Venmo, in-person.
- Mutual credit: ledger-based IOUs recorded in fiat value.
- RHEO: used for fees and optional value transfer.

> Users do not need to hold RHEO directly. Required fees flow through social trust chains, ultimately originating from FOAF holders who stake to generate RHEO. Each intermediary earns a small premium. This makes participation seamless and compensates liquidity providers.

---

## Token overview

### FOAF token

- Contract: ERC-20 on Ethereum, deployed December 2018
- Address: [`0x51300E946bcd4850Db3bE28D1FcC4076Ba4a9288`](https://etherscan.io/token/0x51300E946bcd4850Db3bE28D1FcC4076Ba4a9288)
- Purpose: governance and staking
- Supply: 25,000,000, indivisible, fixed
- Current status: 100% held by the Foundation, never distributed

FOAF is freely tradeable. Stakers choose their commitment level through one of two staking variants:

vFOAF (vote-escrowed FOAF). Stake FOAF, receive vFOAF at 1:1, unstake any time. Provides basic voting rights and standard RHEO generation. Targeted at new users and casual participants.

rFOAF (rooted FOAF). Time-lock FOAF for 6 months to 2 years or longer. Provides enhanced voting weight, higher RHEO generation, and qualifies the holder for additional governance tiers. Targeted at core community members and long-term stakeholders.

Both vFOAF and rFOAF are non-transferable. They represent staking positions, not tradeable derivatives.

### RHEO token

- Purpose: required utility token for platform fees and optional settlement
- Supply: dynamic, managed by algorithmic treasury policy
- Valuation: floating; targeting a ~$1 CAD reference rate for fee calculations
- Generation: created via FOAF staking at a rate determined by DAO governance
- Policy management: treasury uses formula-driven burns and airdrops to keep network liquidity in range
- Use cases: paying fees (transaction, markup, routing), flowing through trust networks to enable access, compensating intermediaries

RHEO is non-transferable. It is consumed at the moment of use through a trust-graph chain that records bilateral credit obligations on the consumer's side. There is no DEX market for RHEO and there shouldn't be: anyone with FOAF can mint their own.

---

## Algorithmic RHEO monetary policy

The 3M FOAF treasury stake generates substantial RHEO (around 12,000 daily at full rFOAF lock), which gives the Foundation room to actively manage monetary policy.

### Policy triggers

Expansionary triggers (airdrops):

- High transaction volume but users running low on RHEO
- New-user onboarding waves requiring liquidity
- RHEO price above target range, where cooling speculation is warranted
- Network congestion from RHEO scarcity

Contractionary triggers (burns):

- RHEO velocity declining (hoarding detected)
- Excess treasury RHEO from transaction fees
- RHEO price below target range
- Network health metrics indicating oversupply

### Monthly policy formula

The treasury computes a policy signal each month from a basket of network metrics:

- RHEO velocity
- Transaction volume trend
- Average user balance
- RHEO price deviation from target
- New-user onboarding rate

When the expansion signal exceeds threshold, the treasury airdrops 0.5 to 2.0 RHEO per active user. When the contraction signal exceeds threshold, the treasury burns 5 to 15 percent of monthly treasury RHEO generation.

The benefits of this approach:

- Self-stabilizing. Responds to network conditions automatically without manual intervention.
- Transparent. The formula is public and DAO-governed.
- User-friendly. Maintains optimal liquidity without users needing to do anything.
- Sustainable. Prevents both scarcity crises and inflation over time.

---

## FOAF allocation (25M supply)

| Purpose | Allocation | FOAF | Notes |
|------------------------|------------|--------------|--------------------------------------------------|
| Community Airdrops | 32% | 8,000,000 | Distributed via custodial wallets for UX |
| Seed Rounds | 40% | 10,000,000 | Seed 1: 5M, Seed 2: 5M (friends/family → international) |
| Team & Advisors | 16% | 4,000,000 | Milestone-based vesting |
| Treasury & Operations | 12% | 3,000,000 | Development, partnerships, governance |

### Distribution strategy

Phase 1: Canadian bootstrap, 2026 Q1–Q2. Friends-and-family seed round of $50K to $150K under exemption rules. Funds personal runway and the international incorporation costs that come next.

Phase 2: international launch, 2026 Q3–Q4. Foundation incorporated in Dubai DIFC. Global accredited investor sales as a regulatory-compliant token offering.

Phase 3: community distribution, 2026–2027. Each verified new user receives 5 vFOAF through a custodial wallet (the "Five FOAF" airdrop). Five vFOAF generates roughly 0.15 RHEO monthly at the light usage tier. Treasury RHEO supplements the base generation through algorithmic airdrops as needed. Internal accounting handles all of this until withdrawal, so there are no gas costs and no blockchain complexity exposed to the user. Progressive decentralization on the UX side lets users learn the underlying mechanics at their own pace.

---

## Fees and RHEO circulation

### Trade-related fees, denominated in RHEO

- Transaction fee: 3% of total trade value, paid by the seller or profit-maker.
- Multi-hop routing fee: 3% of intermediary markup.
- RHEO routing premium: 1% of RHEO passed per hop.

These rates are starting points. Final values are DAO-governed and may be adjusted as the network matures.

### Fee routing logic

Fees flow transparently through social trust chains. Each intermediary earns a 1% routing premium. The originating FOAF holder receives the full RHEO value. The end-user accrues small, fair obligations across the chain rather than confronting a single fee.

---

## Why this structure works

The people who need to use the system do not need to understand its tokenomics. Fees are denominated in fiat, paid through trust chains that source RHEO from FOAF stakers, and routed transparently. Stakers earn RHEO that funds their participation and is consumed by network use. Nobody is gaming a speculative side market. The token economics serve operations, not the other way around.

The architecture is also scale-continuous. The same primitives that handle a backyard gardener sharing zucchini handle a regional food distributor managing commercial farm-to-table supply. The protocol does not bifurcate into community and enterprise tiers.

---

## Custodial wallet design

For community airdrops, users receive vFOAF allocations in app-managed wallets. Internal accounting handles the bookkeeping until a user chooses to withdraw to self-custody. This eliminates gas funding costs (estimated $200K+ saved versus direct on-chain airdrops) and gives users immediate governance and utility access without requiring crypto literacy.

The progressive-decentralization arc is the key UX insight. Users start with everything managed for them, learn the underlying mechanics through participation, and move toward self-custody at their own pace once they have reason to.

---

## Sybil resistance

As the network grows and FOAF becomes tradeable on open markets, the airdrop pool becomes an attractive target for sybil farming, where attackers create networks of fake accounts to harvest free tokens. No single mechanism fully prevents this. The protocol's defense is to make the cost of farming exceed the reward at every scale.

Four mechanisms work together.

Vouching with stake at risk. New accounts enter the network through vouching by existing participants. The voucher places FOAF at stake; if the new account is later determined to be a sybil, that stake is slashed. Creating ten fake accounts requires either one participant risking their stake on all ten, or recursively building a vouching chain, which itself requires real FOAF at every step.

Diverse-counterparty requirements. Self-custody unlock is not satisfied by transaction count alone. The protocol requires interaction with a minimum number of distinct counterparties drawn from outside the entrant's own vouching cluster. This forces a sybil graph either to connect outward to real users (who can decline to trade) or to keep extending its own fake graph at increasing vouching cost.

Graph-topology detection. Sybil clusters have detectable signatures: high internal connection density, low external connectivity, time-correlated activity, shared device fingerprints, geometrically clean transaction amounts. The protocol flags suspicious clusters for tighter unlock rules and slower release schedules.

Real-world entry friction. First entry to the network requires a signal that is costly to fake at scale: phone verification, in-person meet at a community node, QR onboarding at a verified physical location. This does not stop determined attackers but raises the bar enough that casual farming is not worth attempting.

Beyond these mechanisms, the late-cohort airdrop floor itself acts as a deterrent. When the per-signup airdrop drops to its minimum, sybil farming pays only if the FOAF market price exceeds the marginal cost of creating each fake account (vouching collateral, time, slashing risk). For small enough payouts, no rational attacker bothers.

There is also a structural advantage that follows from the protocol's shape. FOAF is itself a real-world social trust graph. Sybil clusters that do not connect to that graph are structurally self-isolating. They can game internal metrics but cannot access real value flow. There are no real trades happening, no real fees being consumed, no real network effects accruing to their accounts. They can still dump unlocked FOAF on the open market and extract value from the network's reputation, but the cost of building a sybil graph large enough to do so substantially exceeds what they can extract.

The protocol assumes attackers will try to game any single rule. It is designed so that defeating any one rule does not give the attacker the others. Sybil resistance is a property of the graph, not of any single transaction.

---

## Multi-chain architecture

Ethereum: original 2018 contract, treasury management, regulatory legitimacy.

Radix: primary utility layer for staking, governance, and RHEO operations. The protocol's eventual home.

Bridge: an official Hyperlane warp route moves FOAF between chains as needed.

---

## Road ahead

- 2026 Q1–Q2: friends-and-family bootstrap funding.
- 2026 Q3: international entity setup in Dubai DIFC.
- 2026 Q4: global token offering and community airdrops.
- 2027 onward: full protocol launch on Radix with governance transition to a Marshall Islands DAO.

For more detail, see [Fee Structure](./fee-structure.md) or [DAO Transition](./dao-transition.md).
