# The peer-to-peer architecture

## Status

The current GrowOperative production is a centralized Rails service backed by MySQL. It works for the controlled launch in Crawford Bay, BC. It does not work as a long-term description of what FOAF actually is. The protocol is at root about bilateral relationships between known parties (credit between people who chose each other), and a central database is an implementation expediency, not a representation of the truth.

The medium-term direction is a peer-to-peer architecture where bilateral state lives between the parties involved, the chain carries anchors and tokens but not the credit graph itself, and routing decisions for multi-hop payments are computed by relays without the relay having to be trusted with the underlying state.

This track's design is the least locked-in of the three. Direction is set; the specific protocol choices are open.

## The objective

Move the credit graph from "everything in a central database" to "bilateral state held by the parties, with optional anchoring to chain and pluggable routing infrastructure." The end state has these properties:

- Two parties in a credit relationship hold the same authoritative state, signed by both. The state does not need a third party to be true.
- A relay can index public-facing data (offers, discovery, routing graph) without seeing private credit balances.
- Multi-hop payments can be computed by any relay that has a graph view, with the computation result being a route proposal that the parties along the route then sign individually.
- Anchoring to Radix is optional and triggered by parties that need it (high-value trades, dispute escrow, regulatory traceability), rather than required for every operation.

## What needs to be built

A bilateral state machine that can be implemented identically on multiple platforms (web, iOS, Android, server). State updates are signed by both parties; rejected updates are rejected; orphaned proposals time out. This is the core data model and the part where shared spec quality matters most.

A relay protocol. Relays maintain a public view of the credit graph (which trustlines exist between which parties, with what limits) without seeing transaction-level state. Trustline existence is public; balances are not. Discovery, offer surfacing, and pathfinding all happen at the relay layer.

A routing layer. Multi-hop payment proposals computed against graph state, returned as proposed route plus parameters. The parties along the route then sign or reject individually. The route does not commit until all signatures are in.

An anchoring path. Parties can post a hash of their bilateral state to Radix Babylon at any time, creating a tamper-evident commitment. Optional and triggered, not required.

An optional on-chain settlement path. For trustlines that need full on-chain proof (high-value trades, escrow scenarios), there's a way to migrate a specific trustline from bilateral-private to on-chain, using the Scrypto staking infrastructure as a security layer.

The seam between this work and the protocol stack on Radix is anchoring. This work owns everything off chain. The Scrypto track owns the chain side. The interface between them needs collaborative design.

## What is not in scope

The following are adjacent but separate:

- The Hyperlane bridge (covered in [Bringing FOAF to Radix](radix-bridge.md))
- The Scrypto protocol stack (covered in [Building the FOAF protocol stack on Radix](scrypto-protocol.md))
- The custodial wallet system for non-crypto-native users
- Subnet relay business logic (relevant later, not now)

## Why this is interesting work

Honest reasons.

P2P bilateral-state systems are conceptually adjacent to Lightning, Holepunch's Hypercore Protocol, parts of Veilid, and Nostr's relay model. There is meaningful work in this space but very few production deployments where real users move real value bilaterally. Most of what exists is research or hobbyist. FOAF intends to ship.

The constraints are unusually concrete. Real users in Crawford Bay are using the centralized version right now. The migration target is not abstract; it has to handle actual ongoing trades and not lose history. That kind of constraint is rare in distributed-systems work and produces better designs than greenfield projects do.

The design space is open. Choosing between, for example, a Hypercore-based feed of mutually-signed updates, a CRDT-based bilateral state, or a pure event-sourced approach, is genuinely an open question. A contributor with a strong opinion has room to shape the answer.

The chain is optional, not central. Most protocols built around a chain end up being chain-shaped. FOAF is bilateral-shaped first; the chain is a tool that some operations use. That inversion is rare and pleasant to work in.

## What is offered

Compensation is a FOAF allocation with vesting, drawn from the 16% team-and-advisors pool. Size is negotiated case by case. The default structure is a 6-month cliff with milestone-based unlocks across 12 to 24 months. Cash compensation only if tax or regulatory constraints make token allocation impossible.

Public attribution. A working relationship with the Foundation founder. Continuing involvement welcome but not required.

## What is expected

Demonstrated experience with peer-to-peer or distributed-systems work. The specific stack is open (libp2p, Hypercore Protocol, Pears, Nostr-relay-style, Veilid, custom), but the contributor should have shipped at least one P2P system and understand why the typical web-shaped patterns do not apply here.

Comfort with cryptographic primitives at the application level: signature verification, hash chains, key management for non-crypto-native users. Not protocol cryptography (you do not need to design a new signature scheme), but applied cryptography in the bilateral-state context.

Interest in deploying for real users. This is not a research project. The output has to handle ongoing trades for people in Crawford Bay without losing data.

Willingness to document. The shape of what gets built will inform the protocol's identity for years. If the design is good but the documentation is bad, it does not last.

Communication on a reasonable cadence. Async is fine; weeks of silence is not.

## How to start a conversation

Through the Radix community channels where this entire effort is being assembled, or directly via the Foundation contact link. First conversation is just a conversation. No commitment, no application form, no interview process.

If your background is in P2P systems but not in Radix, that's fine. The chain side is not your part. We need the bilateral state right.
