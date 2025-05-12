# FOAF Foundation Technical Architecture

The FOAF Foundation powers a decentralized trade network through its growing suite of tools. The architecture supports trust-based value exchange using mutual credit, social routing, and transparent fee flows. It is designed to scale from small groups to entire communities while keeping participation simple and accessible.

This document outlines the structure behind GrowOperative and the broader FOAF Marketplace. All components are built to support pricing in local currencies, multi-path trust routing, and smooth onboarding without technical knowledge.

---

## System Overview

- **Progressive Web App**  
  The initial access point for GrowOperative. The PWA will continue to be supported alongside mobile apps.

- **Native Apps (Q2 2026)**  
  Complementary iOS and Android apps with the same features as the PWA, optimized for mobile interaction and offline caching.

- **Backend Infrastructure**  
  Ruby on Rails with MySQL manages listings, trust paths, and fiat-denominated credit records.

- **Blockchain Layer**  
  Smart contracts on Ethereum for FOAF (governance and staking) and RHEO (fee flow, supply regulation, and trust-based routing).

- **Trust Routing Logic**  
  Every user has a contact network. Listings and payments can propagate through trusted connections with dynamic markups and trust-based RHEO forwarding.

---

## Key Components

### Frontend (React)

- Interface for listing, browsing, and fulfilling offers  
- Allows item-level and service listings with unit pricing  
- Controls visibility settings (global or contact-based)  
- Surfaces routing details when intermediaries are involved  
- Embeds video onboarding content

### Backend (Rails and MySQL)

- Stores user records, trades, balances, and trust path metadata  
- Tracks fiat-denominated IOUs for mutual credit  
- Calculates fees and routing flows before invoking blockchain contracts  
- Logs credit creation and settlement timing

### Smart Contracts

- **FOAF**  
  Used for DAO voting and staking. Fixed supply, held by contributors, airdrop recipients, and node operators.

- **RHEO**  
  Used for paying transaction fees. Three percent of trade value is collected, plus one percent per intermediary hop. Users do not need to hold RHEO directly. The system routes it through trust connections automatically.

- Treasury logic is on-chain. Fees are divided as follows:  
  - Fifty percent to node operators  
  - Thirty percent to the DAO treasury  
  - Twenty percent permanently removed from supply

### Trust Path Layer

- Listings can be shared with contacts only or flow through trusted links  
- Intermediaries may apply a markup when relaying an offer  
- Routing fees are embedded transparently into the trade  
- Each hop adds a small RHEO premium (one percent of forwarded value)  
- Credit and reputation scores may evolve into future trust weighting

---

## Data Flow Example

1. Alice lists tutoring at ten dollars per hour  
2. Bob, her direct contact, forwards this offer to Clara at twelve dollars per hour  
3. Clara accepts the trade. She owes Bob twenty-four dollars in credit  
4. Bob owes Alice twenty dollars  
5. RHEO fees are applied automatically. Each participant receives or pays their share  
6. The backend stores balances and syncs with the blockchain as needed

---

## Scalability and Flexibility

- **Multi-Region Support**  
  Local fiat pricing adapts to any region

- **Trust-Driven Growth**  
  Communities grow through relationships, not marketing

- **Lightweight Infrastructure**  
  Backend handles user-facing load, while the blockchain handles governance and fee flows

- **Flexible Onboarding**  
  Users can access the system through PWA, mobile apps, or via trusted node operators

---

## Privacy and Security

- **Pseudonymous Participation**  
  Users may interact with the system using wallet addresses or anonymous handles

- **Encrypted Records**  
  Trade data is stored securely in MySQL with encrypted fields for credit balances and contacts

- **Audited Contracts**  
  FOAF and RHEO contracts will be externally reviewed before major releases

---

Explore more in [technical roadmap](./roadmap.md), [tokenomics](../foaf-foundation/tokenomics.md), and [fee structure](../foaf-foundation/fee-structure.md).
