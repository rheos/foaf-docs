# FOAF Foundation Tokenomics

The **FOAF Foundation** supports local trade and community resilience through a dual-token system designed for real-world utility, not speculation.

## Token History and Legitimacy

**FOAF tokens already exist!** The FOAF contract was deployed to Ethereum mainnet in **December 2018** at address [`0x51300E946bcd4850Db3bE28D1FcC4076Ba4a9288`](https://etherscan.io/token/0x51300E946bcd4850Db3bE28D1FcC4076Ba4a9288). This 7-year development history provides regulatory legitimacy and demonstrates long-term commitment to the protocol vision.

We use two tokens:
- **FOAF** – a fixed-supply governance and staking token (existing since 2018)
- **RHEO** – a flexible-use utility token for transaction fees and trust-based trade settlement

This document outlines how both tokens support the GrowOperative app and broader FOAF marketplace — launching with a multi-location rollout beginning in **Crawford Bay, BC (May 2026)**.

---

## How It Works

GrowOperative helps people trade food, goods, and services — with or without cash. Listings are priced in local currency (e.g., $2 CAD per pound of tomatoes), and trades can settle in:

- **Cash (broadly defined)** – via eTransfer, PayPal, Venmo, or in-person
- **Mutual Credit** – ledger-based IOUs recorded in fiat value
- **RHEO** – used for fees and optional value transfer

> Users do not need to hold RHEO directly. Required fees flow through social trust chains, ultimately originating from FOAF holders who stake to generate RHEO. Each intermediary earns a small premium. This makes participation seamless and compensates liquidity providers.

---

## Token Overview

### FOAF Token
- **Contract**: ERC-20 on Ethereum (deployed December 2018)
- **Address**: [`0x51300E946bcd4850Db3bE28D1FcC4076Ba4a9288`](https://etherscan.io/token/0x51300E946bcd4850Db3bE28D1FcC4076Ba4a9288)
- **Purpose**: Governance and staking
- **Supply**: 25,000,000 (indivisible, fixed)
- **Current Status**: 100% held by original creator, never distributed

**Two-Tier Staking System:**

**vFOAF (Vote-Escrowed FOAF) - Simple Staking:**
- Stake FOAF → get vFOAF instantly, unstake anytime
- Basic voting rights + standard RHEO generation
- Target: New users, casual participants

**rFOAF (Rooted FOAF) - Commitment Staking:**
- Time-lock FOAF for 6 months to 2+ years
- Enhanced voting weight + higher RHEO generation + protocol revenue share
- Target: Core community, long-term stakeholders

FOAF tokens are freely tradeable. Users can choose their commitment level through vFOAF (flexible) or rFOAF (time-locked with better rewards).

### RHEO Token
- **Purpose**: Required utility token for platform fees and optional settlement
- **Supply**: Dynamic, managed by algorithmic treasury policy
- **Valuation**: Floating; targeting ~$1 CAD reference rate for fee calculations
- **Generation**: Created via FOAF staking at rate determined by DAO governance
- **Policy Management**: Treasury uses formula-driven burns and airdrops to optimize network liquidity
- **Use**:
 - Pay fees (transaction, markup, routing)
 - Flow through trust networks to enable access
 - Compensate intermediaries

## Algorithmic RHEO Monetary Policy

**Treasury as Central Bank:** The 3M FOAF treasury stake generates substantial RHEO (~12,000 daily at full rFOAF) which enables active monetary policy management.

### Policy Triggers

**Expansionary (Airdrops):**
- High transaction volume but users running low on RHEO
- New user onboarding waves requiring liquidity
- RHEO price above target range (cool speculation)
- Network congestion from RHEO scarcity

**Contractionary (Burns):**
- RHEO velocity declining (hoarding detected)
- Excess treasury RHEO from transaction fees
- RHEO price below target range
- Network health metrics indicate oversupply

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

## FOAF Allocation (25M Supply)

| Purpose | Allocation | FOAF | Notes |
|------------------------|------------|--------------|--------------------------------------------------|
| Community Airdrops | 32% | 8,000,000 | Distributed via custodial wallets for UX |
| Seed Rounds | 40% | 10,000,000 | Seed 1: 5M, Seed 2: 5M (friends/family → international) |
| Team & Advisors | 16% | 4,000,000 | Milestone-based vesting |
| Treasury & Operations | 12% | 3,000,000 | Development, partnerships, governance |

**Distribution Strategy:**

**Phase 1 - Canadian Bootstrap (2026 Q1-Q2):**
- Friends & Family exemption: $50K-$150K
- Use for personal runway + international incorporation costs

**Phase 2 - International Launch (2026 Q3-Q4):**
- Dubai DIFC or Singapore incorporation
- Global accredited investor sales
- Regulatory-compliant token offering

**Phase 3 - Community Distribution (2026-2027):**
- **"Five FOAF" airdrops** - each new user receives 5 vFOAF via custodial wallets
- **Base RHEO generation** - 5 vFOAF generates ~0.15 RHEO monthly (light usage tier)
- **Treasury RHEO supplements** - algorithmic airdrops provide additional RHEO as needed
- **Internal accounting** until user withdrawal - no gas costs or blockchain complexity
- **Progressive decentralization** UX - users learn at their own pace

---

## Fees and RHEO Circulation

### Trade-Related Fees (in RHEO)
- **Transaction Fee**: 3% of total trade value (paid by the seller or profit-maker)
- **Multi-Hop Routing Fee**: 3% of intermediary markup
- **RHEO Routing Premium**: 1% of RHEO passed per hop

### Fee Routing Logic
- Fees flow transparently through social trust chains
- Each intermediary earns a 1% routing premium
- The originating FOAF holder receives full RHEO value
- The last party (end-user) accrues small, fair obligations across the chain

---

## Why It Works

- **Accessible**: No crypto experience required; fiat pricing and peer-based flow make it usable by anyone
- **Fair & Scalable**: Fees match value created, not flat rates
- **Sustainable**: Network rewards stakers and contributors
- **Decentralized**: FOAF staking anchors the system; RHEO circulates on demand

---

## Custodial Wallet Innovation

**Capital Efficient Distribution:**
- Users receive vFOAF allocations in app-managed wallets
- Internal accounting - no blockchain transactions until withdrawal
- Eliminates gas funding costs ($200K+ saved vs direct airdrops)
- Immediate governance + utility access, optional self-custody

**User Experience:**
- Zero crypto knowledge required
- Progressive decentralization - learn at your own pace
- Withdraw to self-custody after demonstrated participation

## Sybil Resistance

As the network grows and FOAF becomes tradeable on open markets, the airdrop pool becomes an attractive target for sybil farming — attackers creating networks of fake accounts to harvest free tokens. No single mechanism fully prevents this; the protocol's defense is to make the cost of farming exceed the reward at every scale.

**Four mechanisms work together:**

**1. Vouching with stake at risk.** New accounts enter the network through vouching by existing participants. The voucher places FOAF at stake; if the new account is later determined to be a sybil, that stake is slashed. Creating ten fake accounts requires either one participant risking their stake on all ten, or recursively building a vouching chain — which itself requires real FOAF at every step.

**2. Diverse-counterparty requirements.** Self-custody unlock is not satisfied by transaction count alone. The protocol requires interaction with a minimum number of distinct counterparties drawn from outside the entrant's own vouching cluster. This forces a sybil graph to either connect outward to real users (who can decline to trade) or keep extending its own fake graph at increasing vouching cost.

**3. Graph-topology detection.** Sybil clusters have detectable signatures: high internal connection density, low external connectivity, time-correlated activity, shared device fingerprints, geometrically clean transaction amounts. The protocol flags suspicious clusters for tighter unlock rules and slower release schedules.

**4. Real-world entry friction.** First entry to the network requires a signal that is costly to fake at scale: phone verification, in-person meet at a community node, QR onboarding at a verified physical location. This does not stop determined attackers but raises the bar enough that casual farming is not worth attempting.

**Pragmatic floor.** Beyond these mechanisms, the late-cohort airdrop floor itself acts as a deterrent. When the per-signup airdrop drops to its minimum, sybil farming pays only if the FOAF market price exceeds the marginal cost of creating each fake account (vouching collateral + time + slashing risk). For small enough payouts, no rational attacker bothers.

**Structural advantage.** FOAF's protocol is itself a real-world social trust graph. Sybil clusters that do not connect to that graph are structurally self-isolating — they can game internal metrics but cannot access real value flow. There are no real trades happening, no real fees being consumed, no real network effects accruing to their accounts. They can still dump unlocked FOAF on the open market and extract value from the network's reputation, but the cost of building a sybil graph large enough to do so substantially exceeds what they can extract.

The protocol assumes attackers will try to game any single rule. It is designed so that defeating any one rule does not give the attacker the others. Sybil resistance is a property of the graph, not of any single transaction.

## Multi-Chain Architecture

**Ethereum:** Original 2018 contract, treasury management, legitimacy
**Radix:** Primary utility layer for staking, governance, RHEO operations
**Bridge:** Official bridge to move FOAF between chains as needed

## Road Ahead

**2026 Q1-Q2:** Friends & family bootstrap funding
**2026 Q3:** International entity setup (Dubai/Singapore)
**2026 Q4:** Global token offering + community airdrops
**2027+:** Full protocol launch on Radix with governance transition

Learn more in [Fee Structure](./fee-structure.md) or [DAO Transition](./dao-transition.md).
