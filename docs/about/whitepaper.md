# FOAF Foundation Whitepaper

## Introduction

Most people have something to offer their neighbors. Most people need something their neighbors could provide. The thing in the way is usually money, and not having enough of it.

FOAF is a protocol for trade between people who trust each other, or who trust someone who trusts them. It uses mutual credit instead of cash, routed through real social relationships instead of payment processors. This paper describes what is being built, why it has to be built this way, and how we get there.

---

## Vision

A working local economy does not require everyone to have money. It requires everyone to have something to offer and somewhere to offer it. The protocol exists to provide that somewhere.

When someone grows more food than their household can eat, that surplus has value. When someone fixes their neighbor's bicycle, that has value. When a restaurant needs microgreens and a farmer down the road has them, that has value. The work the protocol does is to record and route the value, so that none of it has to evaporate just because the cash to settle is not in the room.

The longer-term picture: communities that can feed themselves and trade with themselves through networks they actually control. Not because cash and banks have failed, but because for billions of small exchanges those rails were always overkill.

---

## Why prior attempts have failed

The idea behind FOAF is not new. LETS, time banks, Ithaca HOURS, FairCoin, Trustlines, and a long list of other community currency and mutual credit projects have tried versions of it for forty years. Most are gone. The few that survive at scale, like WIR Bank in Switzerland and Sardex in Italy, work only between businesses, not between regular people in cash-rich economies.

There are four reasons community-scale attempts have failed, and each one is a design constraint the protocol was built around.

The first is no native demand. Most attempts asked users to adopt mutual credit as the use case itself: bill splitting, friend IOUs, time banking. There was nothing underneath it pulling people in. People had to be sold on mutual credit before they had any reason to use it. The successful systems all had a real underlying need that mutual credit happened to lubricate. Businesses needed cash flow smoothing. Cash-scarce communities needed any form of exchange at all. Without that pull, no network ever reached density.

The most striking case is Stellar. The chain has run continuous peer-to-peer trustline infrastructure and multi-hop pathfinding since 2014, with technical primitives essentially identical to what community mutual credit needs. It is alive, in active use, and its trustline graph contains millions of accounts. The peer-to-peer use case never emerged anyway. The trustlines that exist are between users and institutional anchors moving stablecoins and remittances, not between neighbors. The infrastructure was right and the application layer never showed up.

Native demand is only the precondition. The second failure mode is uncompensated coordination. Volunteers ran the systems, and volunteers eventually quit. Every long-running community currency hit this wall. The work of connecting people, vouching for them, and resolving disputes is real labor, and asking people to do it for free for years is asking too much.

The third is no enforcement against free riders. When someone could accumulate debt and walk away with no consequence, honest participants stopped extending credit, and the network seized up. The systems that worked at scale either had institutional backing (WIR is a Swiss bank) or operated in tight communities where reputation alone was enforcement enough.

The fourth is required crypto literacy. The blockchain-era attempts solved the enforcement problem with smart contracts but introduced a new one. Users had to understand wallets, gas, tokens, and signing. For a network meant to include the cash-poor and the technically casual, that is fatal.

The protocol addresses each of these by design. The application layer creates the native demand. Stakers and routing intermediaries are paid in network-issued credit, so coordination is compensated. New participants enter through vouching by existing participants whose stake is at risk, so free-riding has consequences. Custodial wallets and fiat-denominated pricing mean users never have to think about crypto.

---

## How FOAF works

FOAF is a protocol with a real-world social trust graph underneath it.

Users have contacts. They extend each other credit lines, formally or informally ("I trust you up to $200"), and these credit lines form a graph. When someone wants to trade with someone they do not directly know, the protocol routes the value through a chain of mutual contacts. Each intermediary sees only the segment of the trade adjacent to them. The transaction settles when each pair along the chain updates their bilateral balance.

The flow is:

1. Post. A user lists something they want to offer or something they need.
2. Propagate. The listing reaches other users through their shared contact graph, surfacing only when a real social path exists.
3. Settle. When a match is made, value routes through the trust path. Settlement happens in mutual credit, in cash, or in some combination both parties agree on.

The credit ledger uses local fiat as its unit of account. A pound of tomatoes is worth $2.50. Two hours of garden help is worth $30. The protocol does not introduce a new currency for users to learn. It tracks who owes what to whom, in dollars, and routes the obligations through trust paths until they cancel out or get settled.

Most obligations cancel out. Over time, in a healthy network, debts circulate back to where they started. Maria owes James, James owes Sarah, Sarah owes Maria, and the whole loop dissolves with no money needing to move. This is the deeper logic of mutual credit: not that every debt gets paid, but that most debts cancel themselves through the network's ordinary activity.

---

## GrowOperative as the first application

Food is the first application because food is the keystone good for community-scale mutual credit. Every household either produces it, wants it, or both. It is local, frequent, perishable, and frequently in surplus. It is the closest thing households have to what invoices are for businesses: a steady, varied, recurring stream of value to put through the network.

GrowOperative is a mobile and web app that lets gardeners list surplus produce and arrange exchanges through their existing social network. Behind the app, the protocol routes the trades through trust paths instead of payment rails.

The choice of food is not arbitrary. The marketplace-first principle is what every prior community mutual-credit attempt got wrong. Without a real reason to log in, users do not log in. Without users, there is no network. Food creates the reason. The credit infrastructure runs underneath, doing the work users do not need to know about.

GrowOperative is not the end goal. It is the on-ramp. Once the network has density, the same protocol supports services, tools, labor, and any other locally-produced surplus that wants somewhere to circulate.

---

## Token architecture

Two tokens, separate roles.

FOAF is a fixed-supply token deployed to Ethereum in December 2018. Total supply is 25 million, indivisible. FOAF is held by participants and stakers. It is not used for payments. Its purpose is to back the network's operational capacity and govern the protocol.

RHEO is a flexible-supply utility credit. It is generated by FOAF stakers, consumed by network operations, and routed through trust paths to compensate intermediaries. Most users never hold RHEO directly. Fees, when active, originate from FOAF stakers and travel through the network to where they are consumed.

Every participant holds FOAF from the day they join. Custodial wallets handle the holding, the staking, and the RHEO generation invisibly. New users do not buy a token, install a wallet, or learn what a token is. They join the network and the token is already theirs. In early phases, the token cannot be withdrawn or transferred outside the network. It functions as a membership credential and an operational substrate. The shift to self-custody comes later, once the participant has demonstrated real involvement in the network.

This design is what makes the network legally cleaner than direct token sales. Users are not investors. They have not bought anything. They cannot dump on day one. The token becomes liquid for a participant only after they have used it for the purpose the network exists for.

Direct protocol interaction lives at a separate portal at foaf.foundation. Stakers, governance participants, multisig admins, validators, and bridge operators work with the on-chain layer there. The application layer remains protocol-invisible by design. Two surfaces, two audiences, one protocol.

---

## Governance

Power in the network does not scale linearly with token holdings. Operational capacity does. Staking more FOAF generates more RHEO and gives the staker more of the work and more of the reward. But governance weight is structured to be capped, so that no single holder or coalition can dominate decisions.

The model is cooperative rather than plutocratic. Above a threshold of stake, additional holdings do not buy additional votes. The protocol is run on the principle that the people doing the work and the people using the network should jointly govern it, not the people with the largest balance sheets.

This is a deliberate departure from the standard one-token-one-vote model that most crypto governance uses. It is also a deliberate departure from purely democratic models that ignore the value of long-term commitment. The threshold-tiered design rewards staking and longevity without converting them into kingship.

The detailed mechanism (voting tiers, proposal classes, quorum rules) lives in the governance specification. The principle is what belongs here: governance weight is bounded, and the protocol is owned by the people who use it.

---

## Roadmap

The protocol matures in four phases. Each addresses a problem the previous phase could not solve.

Phase 1: Bootstrap. Centralized coordination, fiat-denominated mutual credit, zero protocol fees. The application layer attracts users; the credit infrastructure runs quietly underneath. The goal is density: enough trust paths, enough recurring exchanges, enough circulating surplus to demonstrate the model works without depending on token economics or chain mechanics. FOAF stakers and RHEO are not yet active. The network is sustained by foundation operations and the value users create with each other.

Phase 2: Distribution. FOAF tokens distribute to participants, contributors, and seed supporters. The vFOAF and rFOAF staking tiers go live, generating RHEO. Fees remain at zero to maximize adoption. This phase establishes the FOAF holder base who will back the network's operational capacity once fees activate. Distribution rewards early participation: initial cohorts receive larger allocations than later ones, scaling down toward a floor that ensures every future participant still receives enough FOAF to operate.

Phase 3: Activation. The protocol moves onto chain. Network fees turn on progressively, paid by participants who profit from a transaction (sellers, intermediaries taking markups), never by buyers. Each intermediary on a transaction path earns a routing premium. Fees originate from FOAF stakers elsewhere in the network and travel through their own trust paths to where they are consumed. DAO governance takes effect. Centralized coordination begins to fade.

Phase 4: Decentralization. New applications build on the FOAF protocol: services, tools, labor, supply-chain finance for small producers. Cross-community credit clearing connects subnets. The protocol becomes infrastructure for any local economy that wants it. The original application becomes one of many. The foundation becomes a contributor among many. The protocol no longer needs centralized stewardship to operate.

Each phase only makes sense after the previous one has produced its output. Bootstrap produces density. Distribution produces stakers. Activation produces a self-sustaining economy. Decentralization produces a substrate other applications can build on. Skipping a step means standing up token mechanics on a network with no transaction demand, or activating fees before the network can pay them. Both are common failure modes of prior attempts.

---

## Why it matters

Most local exchange systems have either failed at scale or scaled by becoming the thing they were trying to avoid. The protocol is an attempt to do this without either outcome.

FOAF pays the people doing the actual work of connecting their communities. Every previous attempt at community-scale mutual credit has asked volunteers to coordinate for free, and the volunteers have eventually quit. That is the failure mode the design refuses to repeat.

The protocol is also designed to scale without bifurcating. Most platforms grow by separating their users into a tier with the original product and a tier paying for the version that actually works. The protocol does not have a Pro tier. The community-garden case and the regional farm-to-table case run on the same infrastructure. The same principles that make the network work for two neighbors trading lettuce are the principles that make it work for a hundred orchards distributing fruit across a valley.

The protocol is also separable from any single application. GrowOperative is the first thing built on it, but the protocol is its own layer, operated through its own portal at foaf.foundation. The substrate is available to anyone who wants to build on it, integrate with it, or interact with it directly. The application is one example, not the entire thing.

What the protocol is ultimately for is harder to say in one line. The shortest version: most of what a local economy needs to do, it can do without money, if there is somewhere to do it. Building that somewhere is the work.
