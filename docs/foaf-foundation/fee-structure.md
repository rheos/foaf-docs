# GrowOperative Fee Structure

GrowOperative uses a dynamic, value-based fee system designed to reward network participants, prevent spam, and remain accessible — even for users trading small quantities or low-value goods.

All fees are paid in **RHEO**, the platform's utility token. RHEO has a floating value, but for illustration purposes, we assume **1 RHEO ≈ $1 CAD** during onboarding.

---

## 🔹 Core Fee Types

### 1. Transaction Fee
- **Amount**: 3% of the total trade value
- **Applies to**: All direct trades (e.g., user buys 5 lbs of tomatoes for $10 = 0.30 RHEO fee)
- **Paid by**: Buyer (or deducted from seller's payout)

---

### 2. Multi-Hop Routing Fee
- **Amount**: 3% of the intermediary's markup
- **Applies to**: Any participant acting as a relay in a multi-hop trade
- **Example**:
  - Bob lists tomatoes for $2/lb
  - Peter resells to Paul at $2.50/lb
  - Peter’s markup: $0.50 → Fee = 0.015 RHEO

---

### 3. Action Fees (Minimal, If Applied)
Used only when necessary to limit spam or reflect real workload.

| Action               | Fee (RHEO) | Notes                             |
|----------------------|------------|-----------------------------------|
| Listing an item      | 0.25       | May be waived in early rollout    |
| Claiming a listing   | 0.50       | Optional, used for queueing       |
| Ledgered Credit Entry| 1.00       | Applies when formal IOU is logged |

---

## 🔹 How RHEO Moves

- **RHEO is required for all fees**, but users don’t need to hold it directly.
- When a user initiates a trade, the required RHEO flows automatically from FOAF stakers through the social trust chain.
- The originating FOAF holder is credited, and each intermediary is compensated.

---

### 🌐 RHEO Routing Premium

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

## 🔹 Off-Platform Payments

GrowOperative does **not process payments**. Instead, users handle settlement however they choose:
- eTransfer
- PayPal / Venmo
- Cash at pickup

The payer marks the payment as sent, and the receiver confirms receipt. The app only records the agreement and fulfillment.

---

## 🔹 Fee Distribution Breakdown

All RHEO fees are split as follows:

- **50%** → Node Operators (infrastructure maintainers)
- **30%** → Treasury (development, support, education)
- **20%** → Burned (to regulate RHEO supply)

This model sustains the system without relying on donations or volunteers.

---

## Summary

| Fee Type         | Basis                     | Rate              |
|------------------|---------------------------|-------------------|
| Transaction      | Trade value               | 3%                |
| Routing (Multi-Hop)| Markup on resale         | 3% of markup      |
| RHEO Routing Premium | Per hop RHEO forwarding | 1% of RHEO passed |
| Listing / Action | Flat (if applied)         | 0.25–1.00 RHEO    |

RHEO-based fees ensure fairness, scale with value, and support the ecosystem sustainably.

For more, see [Tokenomics](./tokenomics.md) or [DAO Transition](./dao-transition.md).
