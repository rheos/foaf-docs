# Bringing FOAF to Radix

## Status

The FOAF token has been live on Ethereum since December 2018 at [`0x51300E946bcd4850Db3bE28D1FcC4076Ba4a9288`](https://etherscan.io/token/0x51300E946bcd4850Db3bE28D1FcC4076Ba4a9288). Total supply is 25 million, indivisible, fixed. The supply has never been distributed; the entire allocation is held in a single address controlled by the Foundation.

The protocol's eventual home is Radix Babylon. The first application on the protocol (GrowOperative) is currently running on Rails and MySQL, with a soft launch underway in Crawford Bay, BC. The chain-side migration becomes load-bearing in Phase 3 of the roadmap, when network fees activate and DAO governance takes effect.

For that migration, FOAF needs to exist on Radix. Hyperlane went live on Radix mainnet in August 2025, which is the path.

## Why Radix

The protocol's design and Radix's design point at each other.

Mutual credit comes down to **resources held under conditional authority**. A trustline isn't a balance in a contract; it's a bilateral agreement with rules about who can change what, and under what circumstances. Asset-oriented programming expresses this directly. A trustline can be a resource with badge-gated transfer rules. vFOAF and rFOAF don't have to be custom token contracts imitating ERC-20s; they are resources whose lock-up and decay rules live in the engine itself, not duct-taped on top of a generic balance ledger. The same primitives that make Scrypto pleasant to write make these patterns feel native rather than bolted on.

Cerberus matters here in a non-marketing way. A credit loop spans many trustlines, and on most chains that means a sequence of transactions with all the failure modes of partial execution. On Radix, an atomic transaction across independent components is a single manifest that either commits everywhere or commits nowhere. For a system that needs participants to trust that their credit position changed exactly the way they signed off on, that property is load-bearing.

The lack of Ethereum-style MEV, predictable fees, and fair ordering matter for users who shouldn't have to think about gas auctions or sandwich attacks to trade vegetables with their neighbour. The audience for FOAF is community-scale, not arbitrage-scale. A chain whose default behaviour is "the transaction does what the manifest says" lets the application stay legible to people who aren't going to read a chain explorer.

Governance gets cleaner for the same reason. vFOAF voting power, rFOAF rewards, badge-gated council actions: each is a resource type with its rules baked in, not a fragile pattern stitched together from token transfers and access modifiers. The audit surface shrinks. The wrong actor can't end up holding the wrong authority because the engine itself tracks it.

The team is betting on Radix because the resource model fits what FOAF actually is. If you've been building in Scrypto and looking for a project where asset-oriented programming earns its keep on something more substantive than another DeFi primitive, this is one.

## The objective

Deploy a Hyperlane warp route between Ethereum and Radix Babylon, with FOAF as the bridged asset and a corresponding FOAF resource on Radix that holders can use, transfer, and eventually stake.

The bridge is a protocol-layer capability. It will live behind the protocol portal at foaf.foundation, alongside staking, governance, and other on-chain operations. The consumer-facing GrowOperative application interacts with the protocol invisibly; the portal is where direct on-chain work happens.

## What needs to be built

Three pieces.

A Scrypto resource for FOAF on Radix Babylon. Fungible, fixed supply matching Ethereum, divisibility chosen to match the ERC-20 convention. Metadata fields populated: name, symbol, description, icon URL, website. Access rules configured for the Foundation as initial holder, with admin badges or multisig as appropriate for ongoing operations.

A Hyperlane warp route configuration between Ethereum and Radix, with FOAF as the bridged asset. Lockbox or burn-and-mint mechanics, chosen based on the long-term plan and the Hyperlane patterns most appropriate for an indivisible-supply ERC-20. ISM choice is the meaningful decision here, with the security model spelled out and justified before any mainnet deployment.

Testnet round-trip validation. The bridge needs to be tested end-to-end on Sepolia and Stokenet (or equivalent testnets) with throwaway tokens before FOAF itself is touched. The mainnet deploy happens only after the testnet path works cleanly.

## What is not in scope

The following are protocol-layer concerns that come after the bridge:

- vFOAF and rFOAF staking contracts
- RHEO generation and distribution
- Custodial wallet system for early users
- Trustline credit graph on Radix
- Fee routing logic

Those will be designed and implemented separately, using the bridged FOAF resource as a primitive. The bridge is a prerequisite, not the whole protocol.

## Why this is interesting work

A few reasons that may or may not matter to a given developer.

The FOAF contract has been on Ethereum for over seven years without ever being distributed. Bringing it onto Radix is the moment the token finally enters productive use. That kind of long-dormant on-chain asset doesn't come up often.

The mission is community mutual credit, not speculative DeFi. The protocol is designed for households trading surplus food, not yield farmers. Whether that sounds boring or refreshing depends on the developer.

The Radix ecosystem doesn't yet have many reference cases for bringing an existing ERC-20 across via Hyperlane. Whoever does this well first will get cited.

## What is offered

Compensation is a FOAF allocation with vesting, drawn from the 16% team-and-advisors pool. Size is negotiated case by case based on scope. The default structure is a 6-month cliff with milestone-based unlocks across 12 to 24 months. Cash compensation only if tax or regulatory constraints in your jurisdiction make a token allocation impossible.

Public attribution for the bridge work in the project's documentation and any released materials.

A working relationship with the Foundation founder. Decisions get made in the same conversation, not three weeks later.

Continuing involvement is welcome but not required. A clean engagement that ends when the bridge ships is fine too.

## What is expected

Demonstrated experience with one or both of: Scrypto on Radix Babylon, Hyperlane warp route deployment.

Comfort with end-to-end deployment from testnet through mainnet, including ISM configuration and security tradeoffs.

Willingness to document what gets built, in enough detail that another developer could read it later and understand why the decisions were made.

Communication on a reasonable cadence. Async is fine; weeks of silence is not.

## How to start a conversation

The Foundation is reachable through the Radix telegram channels where this work is being discussed, or directly via the contact link on the Foundation site. The first conversation is just a conversation. There is no commitment expected from either side until both sides have a clear sense of what the work is and what the engagement looks like.

No application form. No interview process. Show up, talk, see if it fits.
