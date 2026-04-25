# GrowOperative Fee Structure

GrowOperative uses a dynamic, value-based fee system designed to reward network participants, prevent spam, and remain accessible — even for users trading small quantities or low-value goods.

All fees are paid in **RHEO**, the platform's utility token. RHEO has a floating value, but for illustration purposes, we assume **1 RHEO ≈ $1 USD (illustrative only)** during onboarding.

---

## Core Fee Types

### 1. Transaction Fee

- **Amount**: 3% of **margin** (sale price minus cost basis)
- **Applies to**: Every sale at every hop — producer-to-consumer, intermediary resale, any transfer of goods for value
- **Paid by**: The seller at each hop
- **Margin** is automatically derived from the item's provenance chain, which records the cost basis at each prior hop

A producer with no upstream cost basis in the system pays 3% on the full sale price. An intermediary who bought at $X and sells at $Y pays 3% on ($Y − $X). A pass-through sale (same price as purchase) incurs no fee. A sale at or below cost incurs no fee.

**Examples**

- Alice grows tomatoes and sells 5 lbs for $10 → fee = 3% × $10 = $0.30
- Bob buys the tomatoes for $10, resells to Peter for $12 → fee = 3% × $2 = $0.06
- Peter resells to Paul at cost ($12, no markup) → fee = $0
- A distributor buys $1,000 of produce, sells for $1,050 → fee = 3% × $50 = $1.50

This is a **value-added (VAT-style) fee model**: every participant pays only on the value they add to the chain, not on the gross transaction. It prevents fees from compounding across long supply chains and keeps thin-margin intermediaries economically viable — which is essential for real-world farm-to-table supply to function on the network.

---

### 2. Action Fees (Used Only if Needed)

GrowOperative aims to minimize friction. Action fees are **disabled by default** and may only be activated if specific abuse patterns or scaling needs arise.

| Action | Fee (RHEO) | Status | Notes |
|----------------------|------------|--------------|-------------------------------------------------------------------|
| Listing an item | 0.25 | *Disabled* | Reserved for potential spam prevention; not charged at launch |
| Claiming a listing | — | *Not used* | No fee; claiming is free unless a reservation system is added |
| Ledgered Credit Entry| — | *Removed* | Formal credit entries are core functionality and should be free |

---

## How RHEO Flows

- **RHEO is required for all fees**, but users don’t need to hold it directly.
- When a user initiates a trade, the required RHEO flows automatically from FOAF stakers through the user’s social trust chain.
- The originating FOAF holder is credited, and each intermediary is compensated.

---

### RHEO Routing Premium

Intermediaries earn a small premium when they help route RHEO through the trust network. This compensates them for extending liquidity and holding temporary obligation.

#### Example (Single Hop):
- Bob holds 1.00 RHEO
- Mary needs 1.00 RHEO
- You are the intermediary
 - You owe Bob: 1.00 RHEO
 - Mary owes you: **1.01 RHEO**
 - You earn: **0.01 RHEO**

#### Example (Multi-Hop):
- RHEO passes through 3 intermediaries, each with a 1% routing premium:
 - Final cost to Mary = **~1.03 RHEO**
 - Each hop earns 0.01 RHEO

This:
- Rewards participation
- Encourages short, efficient trust paths
- Incentivizes users to **hold their own RHEO**
- Drives demand for **owning FOAF to generate RHEO directly**

The default premium is **1% per hop**, configurable by FOAF governance.

---

## Off-Platform Payments

GrowOperative does **not process payments**. Instead, users handle settlement however they choose:
- eTransfer
- PayPal / Venmo
- Cash at pickup

The payer marks the payment as sent, and the receiver confirms receipt. The app only records the agreement and fulfillment.

---

## Fee Distribution Breakdown

All RHEO fees are split as follows:

- **50%** → Node Operators (infrastructure maintainers)
- **30%** → Treasury (development, support, education)
- **20%** → Burned (to regulate RHEO supply)

This model sustains the system without relying on donations or volunteers.

---

## Summary

| Fee Type | Basis | Rate |
|----------------------|------------------------------------------|-------------------|
| Transaction | Margin (sale − cost basis) at each hop | 3% |
| RHEO Routing Premium | Per hop RHEO forwarding | 1% of RHEO passed |
| Listing / Action | Flat (if applied) | 0.25–1.00 RHEO |

RHEO-based fees scale with value *added*, not gross volume — ensuring fairness for every participant and keeping supply chains of any length economically viable.

For more, see [Tokenomics](./tokenomics.md) or [DAO Transition](./dao-transition.md).
