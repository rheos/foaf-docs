# FOAF Foundation Technical Architecture

The **FOAF Foundation** powers a decentralized trading ecosystem through the **Growoperative app** and future **FOAF marketplace**, built on a robust technical architecture. This document outlines the system design, supporting per-unit pricing in local fiat currency (e.g., $2 CAD per lb), flexible trade settlements (cash, mutual credit recorded as fiat IOUs, or RHEO if accepted), and a friend-of-a-friend trust network. The architecture enables the May 2026 alpha in Crawford Bay, BC, and other locations, with explainer videos aiding adoption.

## System Overview
- **Progressive Web App (PWA)**: Initial platform for Growoperative, transitioning to native iOS/Android apps by Q2 2026.
- **Backend**: Ruby on Rails with MySQL for trade data and user management.
- **Blockchain**: Ethereum-based smart contracts for FOAF (governance) and RHEO (fees, settlements).
- **Trust Network**: Friend-of-a-friend model for contacts-only listings, with global visibility option.
- **Media**: Explainer videos hosted on X and YouTube for onboarding and marketing.

## Components
1. **Frontend (React.js)**:
   - User interface for listing items (e.g., “Tomatoes, $2 CAD per lb”), browsing, and trading.
   - Supports global or contacts-only visibility, showing markups for trust network trades.
   - Integrates explainer video embeds for setup, listing, and trading guides.
2. **Backend (Ruby on Rails, MySQL)**:
   - Manages user accounts, listings, and trade history.
   - Stores mutual credit as fiat-based IOUs (e.g., “Paul owes Peter $2.50 CAD”).
   - Handles pricing in local fiat and fee calculations (e.g., 3% RHEO fee).
3. **Blockchain Layer**:
   - **FOAF Contracts**: Manage 25M fixed tokens for staking and DAO voting.
   - **RHEO Contracts**: Handle transaction fees (3%), action fees (e.g., 0.25 RHEO for listing), and burns (20% of fees).
   - Supports pseudonymous interactions via wallet addresses.
4. **Trust Network**:
   - Contacts-only listings propagate through contacts’ contacts, with intermediaries setting markups (e.g., $2.50 CAD per lb vs. $2 CAD).
   - Multi-hop trades incur +0.1 RHEO per hop, tracked on-chain.
5. **External Services**:
   - Video hosting (X, YouTube) for marketing and instructional content.
   - Signal, Telegram, and Facebook APIs for community outreach and notifications.

## Example Trade Flow
- **Listing**: Bob lists “Tomatoes, $2 CAD per lb, 5 lbs” (0.25 RHEO fee), contacts-only.
- **Request**: Paul, via Peter, requests 1 lb at $2.50 CAD (0.5 RHEO claiming fee).
- **Settlement**: Peter collects 1 lb from Bob ($2 CAD, mutual credit), delivers to Paul ($2.50 CAD credit). Fees (0.075 RHEO for Peter, 0.06 RHEO for Bob) apply if RHEO used.
- **Data**: MySQL stores trade details; blockchain records fees and credit settlement (1 RHEO).

## Scalability
- **Multi-Location Support**: Deployable in any community, with localized fiat pricing (e.g., CAD, USD).
- **High Throughput**: Rails/MySQL handles thousands of trades; blockchain offloads non-critical data.
- **Global Reach**: Videos and trust network enable adoption in diverse resilience groups.

## Roadmap
- **2025**: Add payment and mutual credit tracking to PWA, integrate blockchain fees.
- **Q2 2026**: Launch native apps and videos for May 2026 alpha in Crawford Bay and beyond.
- **2027**: Scale to FOAF marketplace, supporting diverse goods/services.

## Security
- **Pseudonymous Access**: Wallet-based logins minimize personal data.
- **Smart Contract Audits**: Ensure FOAF and RHEO contract integrity.
- **Data Privacy**: Encrypt sensitive trade data in MySQL.

Explore more in [roadmap](./roadmap.md) and [tokenomics](../foaf-foundation/tokenomics.md).
