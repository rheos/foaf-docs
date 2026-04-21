# FOAF Ecosystem & Landscape

This document tracks organizations, communities, events, and resources in the broader mutual credit, credit clearing, and collaborative finance space. FOAF does not operate in isolation — knowing who else is building in this space helps us position well, avoid duplication, and identify future collaborators.

---

## Resource Hubs

### lowimpact.org — Mutual Credit Category
**URL:** https://www.lowimpact.org/categories/economy/mutual-credit

A worker co-operative running one of the most comprehensive public resource hubs for alternative economics. Their mutual credit section links out to related topics including:

- Credit clearing
- Credit commons
- Local / independent currencies
- ROSCAs (rotating savings & credit associations)
- Co-operatives and commoning

Useful as a reference for framing, education content, and understanding how the broader public encounters these ideas. Their audience overlaps significantly with FOAF's target users.

---

## Communities & Gatherings

### Collaborative Finance (CoFi) Gathering
**URL:** https://www.collaborative-finance.net

An annual week-long gathering in the Austrian Alps (Commons Hub, Hirschwang) focused on the theory and practice of alternative financial systems. Organized by Matthew Slater, Stephen DeMeulenaere, and Scott Morris — veterans of the community currency and commons economy space.

Past attendees include organizations with direct relevance to FOAF:

| Organization | Relevance |
|---|---|
| **Credit Commons** | Protocol for interoperable mutual credit networks |
| **LedgerLoops** | Multilateral credit clearing / cycle detection |
| **Mutual Credit Services** | UK-based B2B mutual credit operator |
| **Grassroots Economics** | Community currency implementation in Kenya |
| **Circles UBI** | Trust-based UBI on blockchain |
| **Holochain** | Agent-centric distributed computing |
| **Sikoba** | Peer-to-peer IOU / credit network |
| **Celo** | Mobile-first blockchain for financial inclusion |
| **Commons Stack** | Token engineering for commons governance |

**Status:** Aware of CoFi; not attending until iOS/Android apps are released. A working product is a stronger entry point than a pitch.

---

## Parallel Implementations

### VimbisoPay / Credex Ecosystem
**Organization:** Great Sun Group  
**Location:** Zimbabwe (Harare/Mbare), with technical leadership in Halifax, Canada  
**URLs:** https://mycredex.app, https://docs.mycredex.app  
**GitHub:** https://github.com/Great-Sun-Group/credex-core

**Team:**
- Ryan Watson (Founder & CTO, Great Sun Group, based in Halifax)
- Mike Dube (CEO, VimbisoPay & Great Sun Group Zimbabwe operations)

**What They're Building:**

A mutual credit system with remarkably similar architecture to FOAF:

- **Core Mechanism:** "Credex" smart contracts are non-transferable IOUs between two parties. Outstanding credexes automatically chain into "credloops" (credit cycles) which are detected and cleared by their Minute Transaction Queue (MTQ).
- **Zero-Sum Ledger:** All credits and debits balance to zero across the system — identical to FOAF's mutual credit model.
- **Client Apps:** VimbisoPay mobile app and WhatsApp chatbot connect to the credex-core API.
- **Natural Resource Anchoring:** Daily Credcoin Offering (DCO) ties exchange rates to natural resource flows rather than fiat.
- **Secured vs Unsecured:** Can issue credexes backed by real assets (currency, gold) or purely on trust.

**Key Differences from FOAF:**

| Aspect | VimbisoPay/Credex | FOAF |
|---|---|---|
| **Token Model** | Credcoin (DCO-based, resource-anchored) | FOAF (governance) + RHEO (transaction utility) |
| **Blockchain** | None — centralized API/ledger | Radix DLT (planned) |
| **Credit Clearing** | MTQ (Minute Transaction Queue) | Trust-path routing with credloop detection |
| **Philosophy** | "Alternative TO currency" — Steiner-inspired, sovereignty-focused | Trust networks + resilience hubs |
| **Target** | Zimbabwe initially, focus on cash-scarce economies | Community gardens → broader marketplace |

**Development Status (as of March 2026):**

- **Launch Timeline:** Demo announced September 2023 in Mbare, Harare. Actual user adoption unclear.
- **Technical Maturity:** credex-core API exists with documentation. Credloop clearing logic appears implemented.
- **User Base:** No public evidence of active users or transaction volume.
- **Team Size:** Very small (~2-3 visible team members).

**Relevance to FOAF:**

1. **Algorithmic Overlap:** Their MTQ credloop clearing is solving the exact same graph traversal problem FOAF needs to implement. Worth studying their approach even though we can't see their source code.
2. **Shared Challenges:** Both projects face identical obstacles — building trust in mutual credit, user onboarding in low-connectivity environments, and making abstract credit concepts tangible.
3. **Complementary Strengths:** They appear to have built the credloop logic; FOAF has more user-facing work done. Both are MVP-stage with no significant user base yet.
4. **Different Paths:** Centralized API vs. blockchain, resource-anchoring vs. fiat-denominated, philosophical vs. practical framing.

**Potential Collaboration:**

Given similar stage and overlapping problem space, knowledge sharing could be valuable — especially around credloop algorithms, user education, and credit limit management. Both projects would benefit from open dialogue.

---

## Notes on Positioning

- FOAF's trust-path routing and credloop clearing have meaningful overlap with what LedgerLoops and Credit Commons are building. Worth understanding their architectures before any collaboration or differentiation conversations.
- The lowimpact.org "credit clearing" category is particularly relevant to FOAF's credloop logic — their framing of multilateral netting maps directly to what we're implementing.
- CoFi explicitly bridges community currency veterans with web3/blockchain builders — exactly where FOAF sits with the Radix implementation.

---

*Last updated: March 2026*
