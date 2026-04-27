# FOAF as a DeFi protocol

FOAF is a DeFi protocol. The mission distances it from speculative DeFi; the architecture and mechanics place it firmly inside the DeFi taxonomy. This document explains how FOAF qualifies, where it differs from typical DeFi, and why the classification matters.

## What FOAF actually does

The protocol routes credit between participants through a real-world social trust graph. Users extend each other credit lines, formally or informally, and the protocol routes value through chains of those credit lines when two parties want to trade without a direct relationship. Each participant's balance sheet updates in pieces; the network's state is the aggregate of bilateral balances.

The token layer adds operational capacity. FOAF is a fixed-supply staking token. Stakers generate RHEO, a flexible-supply utility credit that pays for network operations. Fees, when active, originate from FOAF stakers and travel through their own trust paths to where they are consumed. Governance is structured to be capped: operational capacity scales with stake, but voting weight does not.

Both layers (the credit-routing layer and the token-economic layer) are DeFi primitives.

## DeFi properties FOAF implements

Credit issuance and routing without traditional intermediaries. Trustlines are bilateral credit instruments. Multi-hop transactions are routed credit instruments. Issuing and routing credit between parties without banks or payment processors is the core DeFi primitive that lending and payment protocols implement.

Pathfinding through a credit graph. The same fundamental mechanism that Stellar, original Ripple, and the Lightning Network use, all of which are classified as DeFi protocols. FOAF's routing is in that lineage, with social trust paths instead of asset-issuer trustlines.

Staking with utility yield. FOAF stakers generate RHEO. Lock a token, earn a flow of utility credits. That is a yield-bearing staking protocol by any reasonable definition. The yield is in operational capacity rather than tradeable rewards, but the mechanism is identical to staking models in many DeFi protocols.

Permissionless on-chain participation. Once the protocol moves onto Radix in Phase 3, anyone can interact with the credit network on-chain without permission. Permissionless access is the defining property of DeFi.

Transparent on-chain settlement. Phase 3 onward runs the credit ledger as on-chain state. Public, auditable, censorship-resistant settlement is a DeFi-defining property.

DAO governance over protocol parameters. Threshold-tiered cooperative governance with on-chain voting. Protocol parameters such as fee rates, RHEO generation rates, validator sets, and ISM choices become community-controlled rather than foundation-controlled. This is the standard DAO pattern of mature DeFi protocols.

Composability. Once on Radix, FOAF resources can be used as collateral, integrated into other applications, wrapped in additional financial products, or built on by third-party developers. The protocol becomes a primitive that other protocols and applications compose with. Composability is one of DeFi's most distinctive properties.

## Where FOAF differs from typical DeFi

Three differences, all about purpose rather than mechanism.

The yield is not speculative. RHEO is consumable utility, not tradeable APY. Staking is for backing operational capacity, not for chasing returns on capital. The token economics are designed for the network to function, not for holders to extract.

The credit graph is socially-routed, not pool-based. Most DeFi credit protocols (Aave, Compound, Maple) use anonymous liquidity pools where lenders and borrowers never see each other. FOAF's credit graph is explicit, named, and built on real-world trust. Different mechanism for assessing creditworthiness, same underlying primitive of routed credit.

The unit of account is local fiat, not a crypto asset. Users see dollars when they price tomatoes. The token layer is invisible to most participants. Most DeFi treats its token as the user-facing asset; FOAF treats its token as protocol substrate.

These are differences in design philosophy, not in category. A DeFi protocol that resists speculation and routes through social graphs is still a DeFi protocol.

## The most accurate subcategory

FOAF can be described accurately as any of four overlapping DeFi subcategories. Each emphasizes a different property of the protocol.

Real-world DeFi (RWA-DeFi). Community mutual credit is a real-world financial primitive that has been operating outside crypto for almost a century: WIR Bank since 1934, Sardex since 2009, RES since 1996. Bringing it onto DeFi rails is the same move Ondo, Centrifuge, and Maple Finance make with traditional financial assets. FOAF does it for community-scale credit.

SocialFi. Financial primitives running over a social graph rather than over anonymous capital pools. The trust-path-routing model is canonical SocialFi territory.

Regenerative finance (ReFi). Mission-aligned DeFi focused on community resilience and local economic regeneration rather than pure yield extraction. FOAF fits this category in spirit even where it does not use ReFi-specific instruments such as carbon credits.

Community DeFi. A newer informal category for protocols that bring DeFi mechanisms to community-scale economic coordination. WIR-style mutual credit on chain is exactly this.

The shortest accurate description, if only one is needed: DeFi infrastructure for real-world community credit.

## Two-layer architecture

FOAF ships with two surfaces that serve two different audiences.

The application layer is the consumer-facing surface. Applications such as GrowOperative use the protocol invisibly: local fiat pricing, custodial wallets, social trust paths, a marketplace experience. Users do not see tokens, gas, signing, or chain state. The application layer is where the protocol meets ordinary users who do not know or care that DeFi is underneath.

The protocol portal at foaf.foundation is the power-user surface. Stakers, governance participants, multisig admins, validators, and bridge operators work there directly. The portal exposes self-custody, FOAF and RHEO balances, staking and unstaking, governance voting, bridge operations, and protocol parameter access.

This is the canonical DeFi-protocol shape. Lido has stake.lido.fi while every integrator wraps it. Aave has app.aave.com while every lending dApp composes with it. MakerDAO has its own portal while CDPs are accessed through dozens of front-ends. A first-party protocol portal alongside multiple application-layer integrations is how mature DeFi protocols ship.

The two-layer architecture is part of what makes the DeFi classification accurate rather than aspirational. The portal is the literal evidence that the protocol exists independently of any single application, and is available to anyone who wants to build on it or interact with it directly.

## Why the classification matters

Three concrete reasons it is worth claiming the DeFi label rather than rejecting it.

Regulatory pathways. Regulators in DIFC and Singapore, and increasingly in the EU, recognize DeFi protocols as a defined category with rules to evaluate against. There are no equivalent rules for "community currency." Calling FOAF a DeFi protocol gives lawyers and regulators something they already know how to look at.

Funding pathways. DeFi-focused VCs, RWA-focused funds, and crypto ecosystem grants are deployable capital that exists right now. A pitch labeled "community currency" usually does not survive their screening filter. A pitch labeled "RWA-DeFi for community credit" does.

Technical ecosystem fit. Hyperlane, Radix, custodial wallet providers, audit firms, on-chain analytics, validator infrastructure: all of it is built for projects that live inside the DeFi taxonomy. A protocol that opts out gives up access to most of the toolchain that already exists.

## Threading the needle

FOAF positions itself against speculative DeFi without rejecting the DeFi category. The framing is: DeFi infrastructure built for real-world community credit, not for yield farming.

Other mission-aligned DeFi projects describe themselves the same way. They use the infrastructure without adopting the speculative culture. The DeFi category is broad enough to include both, and always has been.

The shortest version: FOAF is DeFi by mechanism and DeFi-adjacent by culture. The classification is a description of what FOAF is, not a marketing decision.
