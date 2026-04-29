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
