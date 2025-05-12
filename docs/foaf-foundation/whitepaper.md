# FOAF Foundation Whitepaper

## Introduction

The FOAF Foundation is building a trust-based trading network that helps communities meet their needs without relying on cash or centralized systems. Using mutual credit, social trust paths, and transparent value routing, FOAF empowers people to exchange goods and services directly. This paper outlines the philosophy, architecture, token model, and roadmap behind the project.

---

## Vision

Most people have something to offer, but lack easy ways to trade what they have for what they need. FOAF bridges that gap by replacing the need for cash with social credit and trust. Participants can grow food, fix tools, share skills, and support each other, even when money is tight.

Many past projects have explored similar ideas — systems like Local Exchange Trading Systems (LETS), Community Exchange Systems (CES), and more recently, blockchain-based attempts at peer-to-peer credit and trust. These efforts helped define the space but often failed to scale because of complex interfaces, lack of incentives, or a missing social fabric. FOAF builds on what they introduced, grounding it in real-world relationships and a model where value flows automatically through trust paths.

We are not inventing these ideas from scratch. Mutual credit, community exchange, and reputation-based trust have been explored before. FOAF builds on these insights with tools that are simple, scalable, and rooted in everyday relationships.

---

## GrowOperative and the FOAF Marketplace

FOAF begins with GrowOperative, an app that allows people to list, trade, and share garden produce and household goods. Over time, this grows into the FOAF Marketplace, where people can also offer services, labor, tools, and time.

Everything is priced in local currency, but settled in mutual credit or RHEO. Credit can flow through friends and contacts. RHEO flows automatically through trust chains, so users do not need to hold or understand tokens.

---

## Core Components

- **Mutual Credit**: Trade is tracked as IOUs in local currency. Positive and negative balances are shared transparently within trust paths.
- **Trust Network**: Users can choose to share listings with direct contacts or allow them to flow through extended networks. Intermediaries can apply markups and are rewarded for routing.
- **RHEO**: The utility token used to pay transaction fees. Routed automatically.
- **FOAF**: The governance token used to stake, vote, and shape how the system grows.

---

## Token Model

### FOAF
- Fixed supply of 25 million
- Used for DAO governance and staking
- Distributed through airdrops, contributor rewards, and sales
- Staked tokens can earn voting rights and treasury influence

### RHEO
- No fixed supply
- Used for transaction and routing fees
- Three percent of trade value is paid in RHEO
- One percent per trust hop is added to the routed amount
- Users earn RHEO by participating in trades or staking FOAF
- Fees are distributed: 50 percent to node operators, 30 percent to the treasury, 20 percent burned

---

## Architecture Overview

- Web and mobile clients allow listing, trading, and messaging
- Backend uses Ruby on Rails and MySQL
- Smart contracts on Ethereum track FOAF and RHEO usage
- Trust routing is handled through social graphs built into the platform
- No user is required to hold tokens directly to participate

---

## Governance

FOAF operates as a DAO. Anyone who holds and stakes FOAF can vote on proposals. These include changes to fee structures, new funding requests, expansion plans, and contributor onboarding.

Governance is introduced gradually, starting with proposals from early contributors and expanding to full community control by 2027.

---

## Roadmap Highlights

- 2025: Complete GrowOperative with mutual credit and trust path routing
- Q2 2026: Launch native apps and test multi-location alpha
- Q4 2026: Release FOAF Marketplace prototype with services and tools
- 2027: Begin full DAO governance and expand to global participants

---

## Future Optimizations

As the FOAF network grows, several features are planned to improve efficiency, reliability, and adaptability for more structured or large-scale use cases.

### Credit Loop Resolution

In mutual credit systems, circular debt chains can emerge naturally over time. FOAF will include logic to detect and resolve these loops. When a set of users owe each other in a closed cycle, the system can reduce or eliminate those debts automatically. This helps the overall network remain balanced and improves liquidity by freeing up credit lines without requiring new trades.

### Role-Based Trade Flows

While most users interact through peer-to-peer trust paths, some FOAF deployments may benefit from defined role structures. For example, in supply chains where goods move from producers to processors to vendors, participants may hold roles like grower, packer, or distributor. FOAF will support structured flows in these contexts to clarify responsibilities, manage markups, and allow fine-grained visibility across multi-step trade chains.

### Trust Weighting and Routing Confidence

As the network matures, FOAF may introduce ways to measure and weight the quality of trust paths. Participants who consistently fulfill obligations or route value efficiently may be recognized through reputation signals. These indicators can improve routing logic and give users more confidence when trading with distant connections.

---

These enhancements are planned as part of the system’s long-term growth and will be guided by DAO governance, usage patterns, and community demand.

---

## Why FOAF Matters

People are already helping each other. FOAF gives them a better way to do it. Instead of depending on centralized money or platforms, they can use trust and cooperation to get what they need. This builds stronger communities and reduces financial stress.

FOAF is not a product. It is a protocol for mutual support. The more people use it, the stronger it becomes.

---

Explore more in [tokenomics](../foaf-foundation/tokenomics.md), [fee structure](../foaf-foundation/fee-structure.md), and [contribution](../community/contribution.md).
