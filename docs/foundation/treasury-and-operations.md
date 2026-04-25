# FOAF Foundation Treasury & Operations

This document describes how the FOAF Foundation funds, manages, and sustains ongoing operations. It is a strategic complement to [Tokenomics](./tokenomics.md) and [Fee Structure](./fee-structure.md): where those documents define the token design and fee rates, this document defines the treasury model, revenue streams, operational costs, and sustainability math that make those economics viable in practice.

Target audience: foundation team, advisors, prospective investors, future DAO voters, and anyone evaluating whether FOAF is operationally sustainable.

---

## Goals of the Treasury

The FOAF Foundation treasury exists to:

1. **Fund operations** through the early phases when protocol fees are zero or small.
2. **Hedge against substrate cost volatility** — specifically, rising XRD prices that would otherwise increase the cost of Radix transaction fee sponsorship.
3. **Enable multi-year runway** so the foundation can weather market downturns without forced token sales.
4. **Support ecosystem growth** — grants, partner integrations, community programs.
5. **Transition gracefully to DAO control** with transparent, auditable holdings.

The treasury is not intended to be profit-maximizing. It is intended to make the foundation's mission sustainable over decades, through the phases defined in the [Technical Roadmap](../technical/roadmap.md) and [DAO Transition](./dao-transition.md).

---

## Phase-Dependent Economics

FOAF operates differently at each phase of its roadmap. The treasury strategy adapts accordingly.

### Phase 1 — PoC (current through Q2–Q3 2026)

**Fees:** zero. The GrowOperative app and the FOAF protocol operate with all fee parameters set to zero to maximize adoption.

**Revenue:** zero from protocol fees. The foundation is funded by seed round proceeds (approximately $300K from 20% of FOAF allocation).

**Costs:** development, hosting, small team compensation (partially in vested FOAF), legal and compliance, marketing and outreach. Estimated monthly burn: $15K–$25K depending on team size.

**Treasury composition:** primarily stablecoins (seed round raised in fiat/stablecoins), small FOAF reserve, no XRD yet because Phase 1 runs on Rails/MySQL.

**Key constraint:** the seed round must provide runway through the alpha launch and enough operational buffer to get to Phase 2 (early-to-mid 2026) without forced further fundraising.

### Phase 2 — Chain mirror and FOAF deployment (2026)

**Fees:** still zero on the protocol. FOAF ERC-20 token deployed on Ethereum for strategic round. RHEO not yet active.

**Revenue:** possible strategic round (5–10% of FOAF at higher valuation, ~$125K–$375K). Optional subscriptions from early co-op adopters.

**Costs:** Ethereum contract deployment and audit ($20K–$50K one-time), testnet operations on Radix (minimal), continued team and infrastructure burn.

**Treasury composition:** begins diversifying. Stablecoins primary, small XRD position initiated (to accumulate ahead of Phase 3), ETH or WETH for Ethereum operations, FOAF reserve unchanged.

**Key action:** begin accumulating XRD treasury ahead of Phase 3 deployment.

### Phase 3 — Chain-first on Radix Babylon (Q4 2026+)

**Fees:** may activate during this phase, governed by founder/team decision initially and DAO vote later. Activation criteria: sufficient adoption that fees generate meaningful treasury income without suppressing activity.

**Revenue:** protocol fees (once activated) in RHEO, convertible to XRD via DEX. Subscription revenue from growing co-op base. Potential API revenue from third-party apps consuming FOAF protocol.

**Costs:** Radix transaction fee sponsorship becomes the dominant operational expense. Node operators hold XRD reserves; foundation subsidizes via grants if needed. Infrastructure costs grow with network.

**Treasury composition:** XRD becomes a major holding (40–50% of treasury). Most XRD staked on Radix for 7–12% APY. Stablecoin reserve maintained for fiat expenses. FOAF reserve held for strategic use.

**Key action:** establish treasury management policy, multi-sig controls, quarterly transparency reports.

### Phase 4 — Thin backend / full dApp (2027+, post-Hyperscale)

**Fees:** fully active. Protocol generates meaningful revenue. DAO governance active for parameter adjustments.

**Revenue:** protocol fees, subscriptions, API, marketplace fees across expanded FOAF Marketplace categories.

**Costs:** dramatically reduced per-transaction costs post-Hyperscale mainnet (2027+). Node operator economics ease substantially. Development costs decline as protocol stabilizes.

**Treasury composition:** mature. Mostly XRD (staked), stablecoins for operations, FOAF for governance operations and strategic use, possibly Bitcoin or diversified macro reserve.

**Key action:** transition to full DAO control of treasury decisions.

---

## Revenue Streams

The foundation's revenue portfolio diversifies across several streams, each with different characteristics.

### 1. Protocol fees (RHEO-denominated)

When active, protocol fees generate RHEO flowing to the treasury (30% of fee distribution per the fee structure document).

**Characteristics:** scales with adoption, denominated in RHEO, price-exposed to RHEO/fiat fluctuation.

**Conversion:** treasury converts portion of RHEO to XRD (for Radix fee sponsorship) and to stablecoins (for fiat expenses) via Radix DEXs, balanced against RHEO price and need.

**Critical dependency:** this revenue stream is only operationally useful if RHEO can be reliably swapped for XRD and stablecoins through liquid markets. See [Market and Liquidity](#market-and-liquidity) for how the foundation establishes and maintains that liquidity. If RHEO liquidity is inadequate, fee revenue accumulates on the foundation's books but cannot fund operations.

**Phase:** activates during Phase 3, matures during Phase 4+.

### 2. Seed and strategic token sales

One-time events that fund early operations.

**Characteristics:** lump-sum, fiat-denominated, used to fund multi-year runway.

**Phase:** Phase 1 (seed) and Phase 2 (optional strategic).

### 3. Subscription revenue

Co-ops may subscribe for premium features: admin dashboards, priority support, branded UI, advanced reporting.

**Estimated pricing:** $20–$50/month per cooperative. With 50–200 cooperatives active during Phase 3, this is $12K–$120K/year.

**Characteristics:** recurring, fiat-denominated, stable.

**Phase:** begins late Phase 2, grows through Phase 3+.

### 4. API access

Third-party applications consuming FOAF protocol may pay for premium API access (higher rate limits, historical data, advanced queries, webhook delivery).

**Estimated pricing:** $99–$499/month per API consumer.

**Phase:** meaningful from Phase 4 onward once other apps emerge on the protocol.

### 5. FOAF Marketplace fees

The expanded marketplace (services, tools, labor beyond food) generates the same fee structure as GrowOperative trades.

**Phase:** Phase 4+ as marketplace launches.

### 6. Grants and partnerships

Ecosystem grants (from Radix Foundation, Gitcoin, regional cooperative development programs, food sovereignty grants) supplement revenue without requiring dilution.

**Characteristics:** opportunistic, fiat or crypto-denominated, typically restricted use.

---

## Operational Costs

### Phase 1 (current)

| Category | Monthly | Notes |
|---|---|---|
| Development | $8K–$15K | Partial team, partially paid in vested FOAF |
| Hosting and infrastructure | $200–$500 | Rails/MySQL, Docker, small-scale deployment |
| Legal and compliance | $500–$2K | Averaged; spikes around token sale and structuring |
| Marketing and community | $1K–$3K | Content, events, regional outreach |
| Audits and security | $500–$1K | Averaged; larger in advance of Phase 2 deployment |
| Tools, services, subscriptions | $500 | Dev tools, monitoring, analytics |
| Reserve / unexpected | $2K–$5K | Buffer |
| **Total estimated** | **$12K–$27K** | |

### Phase 3 (Radix deployment)

| Category | Monthly | Notes |
|---|---|---|
| Development | $20K–$40K | Larger team, Scrypto work, mobile app evolution |
| Hosting and infrastructure | $1K–$3K | Node operator infrastructure, Gateway access, indexing |
| XRD fee sponsorship | Variable | At 10K–100K tx/day, $100–$1K/month at Babylon prices |
| Legal and compliance | $2K–$5K | Ongoing regulatory work across jurisdictions |
| Marketing and community | $3K–$10K | Co-op acquisition, community programs |
| Audits and security | $1K–$3K | Continuous audits as protocol evolves |
| Tools, services | $1K | Dev tools, monitoring, analytics |
| **Total estimated** | **$28K–$62K** | Highly dependent on growth |

Post-Hyperscale (2027+), XRD fee sponsorship drops dramatically, easing the cost side of the equation.

---

## Market and Liquidity

Both FOAF and RHEO require liquid markets, for different reasons. Without liquidity, neither token's design goals function: the foundation cannot convert fee revenue to operational currencies, and token holders cannot exit their positions, which eliminates any rational reason to acquire the tokens in the first place.

**RHEO liquidity serves operations.** Protocol fee revenue arrives as RHEO; it must be convertible to XRD and stablecoins to fund foundation expenses.

**FOAF liquidity serves holders and rFOAF participants.** Investors, community members, and people considering locking FOAF into rFOAF (see [Governance](./governance.md)) need to be able to exit their FOAF positions. Without an exit market, no one rationally buys FOAF to lock into rFOAF, which means RHEO is never generated, which means the fee mechanism has no supply side. FOAF liquidity is the foundation of the entire commitment-and-fee economy. (Note: rFOAF itself is non-transferable — "liquidity" here refers to the freely-tradeable FOAF token, not to rFOAF positions.)

This section addresses how both markets are established and maintained.

### RHEO liquidity requirements

A healthy RHEO market requires:

- **At least one primary trading pair on a Radix DEX.** RHEO/XRD is the natural starting pair. Secondary pair of RHEO/stablecoin (e.g., RHEO/xUSDC on a Radix stablecoin) eliminates the two-hop conversion cost for operational swaps.
- **Sufficient pool depth to absorb foundation conversion volume without material slippage.** As a rough target, pool depth should be at least 10x the foundation's monthly RHEO-to-XRD conversion needs. At Phase 3 scale that likely means $100K–$500K equivalent per side of the primary pool.
- **Organic demand from non-foundation actors** — rFOAF holders converting their generated RHEO, node operators converting their RHEO share, traders and speculators participating in price discovery. Without organic demand, the foundation is the only seller and price collapses.
- **Reliable price signal.** RHEO fee pricing depends on a real-time fiat/RHEO exchange rate. Price oracle availability and manipulation resistance are load-bearing for the fee mechanism (see [Fee Structure](./fee-structure.md)).

### DEX strategy

Primary venue expected to be the leading Radix DEX (e.g., Ociswap or successor), pairing RHEO with XRD and later a Radix-native stablecoin. Secondary venue consideration: once the FOAF token bridges between Ethereum and Radix, FOAF has liquidity on Uniswap-class venues. RHEO does not need Ethereum liquidity directly because users never hold RHEO outside the Radix ecosystem.

Listing approach: foundation-initiated liquidity provision. Rather than relying on third-party market makers from day one, the foundation seeds initial liquidity pools from treasury (contributing both RHEO and paired assets). This guarantees a functioning market at launch.

### Initial liquidity provision

At the point RHEO is launched on Radix (Phase 3), the foundation commits a defined portion of treasury to initial LP positions:

- **RHEO/XRD pool:** foundation contributes newly-generated RHEO (from foundation-owned FOAF locked into rFOAF) paired with treasury XRD. Target initial LP: equivalent of $100K–$300K per side.
- **RHEO/stablecoin pool:** foundation contributes RHEO paired with treasury stablecoins. Target initial LP: equivalent of $50K–$200K per side.
- **Lock-up considerations:** foundation LP positions may be time-locked (e.g., 12 months minimum) to signal long-term commitment and prevent rug-pull concerns.

Ongoing LP participation: foundation maintains a minimum liquidity position even after organic LP providers arrive. This creates a floor on market depth that protects operational conversions from being disrupted by liquidity withdrawal during market stress.

### Organic liquidity development

Getting from foundation-seeded liquidity to a self-sustaining market requires attracting third-party liquidity providers:

- **LP rewards.** A portion of treasury-held FOAF may be allocated as LP incentives — rFOAF holders who provide RHEO/XRD liquidity earn additional FOAF or RHEO over time. Standard DeFi bootstrap mechanism. Can be phased down as organic trading volume grows.
- **Arbitrage opportunities.** If RHEO is listed on multiple venues (multiple Radix DEXs, eventually cross-chain), arbitrageurs naturally provide liquidity and tighten spreads.
- **rFOAF-to-LP pipeline.** rFOAF holders accumulating RHEO naturally become LP providers if LP yields exceed simple holding. Well-designed LP rewards direct this flow toward deepening pool liquidity.

### Foundation conversion practice

When converting RHEO to XRD or stablecoins for operations, the foundation follows practices that minimize market impact:

- **Dollar-cost averaging.** Large conversions are split across time rather than executed as single large swaps. Reduces slippage and avoids signaling large sells.
- **Off-peak execution.** When possible, conversions execute during low-volume periods to minimize price impact on active traders.
- **Pre-committed rules.** Conversion policy is documented publicly (e.g., "foundation converts RHEO to operational currencies quarterly, split across 30-day DCA schedule"). Predictability reduces speculation-driven volatility.
- **Reserve path via LP.** For significant conversion needs, the foundation can withdraw from its LP positions (receiving both sides) rather than trading against the pool, which avoids moving the market.

### FOAF liquidity requirements

A healthy FOAF market requires:

- **Liquid exit path for every FOAF holder.** Seed round investors, strategic round participants, airdrop recipients, team members (post-vesting), and community stakers all need to be able to sell their FOAF. Without this, no one rationally buys in the first place, which breaks the staking economy.
- **Primary trading pair on Ethereum** (initial). FOAF is deployed first as ERC-20 on Ethereum for the seed round. Ethereum liquidity is served by Uniswap or a similar AMM. FOAF/ETH and/or FOAF/stablecoin pairs at minimum.
- **Primary trading pair on Radix** (once bridged). After Phase 3 bridging, FOAF/XRD and FOAF/stablecoin pairs on Radix DEXs. Enables Radix-native users to acquire FOAF without round-tripping through Ethereum.
- **Bridge liquidity.** The cross-chain bridge between Ethereum and Radix requires its own liquidity depth to handle user flows. Slow or thin bridges discourage cross-chain activity.
- **Price discovery and stability.** FOAF price reflects expected RHEO yield from staking plus governance value. Thin markets create volatile pricing that discourages long-term holders.

### FOAF initial liquidity provision

At seed round completion (Phase 1), FOAF is listed on Ethereum DEXs with foundation-seeded liquidity:

- **FOAF/ETH pool:** foundation contributes seed-round-proceeds-denominated ETH paired with foundation-held FOAF. Target initial LP: equivalent of $100K–$250K per side.
- **FOAF/USDC pool:** foundation contributes treasury USDC paired with FOAF. Target initial LP: equivalent of $50K–$150K per side.
- **Lock-up:** foundation LP positions are time-locked (minimum 12 months, possibly 24) to signal long-term commitment and prevent accusations of rug-pull risk.

At FOAF-to-Radix bridging (Phase 3), the foundation extends liquidity to Radix DEXs:

- **FOAF/XRD pool on Radix DEX:** foundation contributes bridged FOAF paired with treasury XRD. Target: equivalent of $100K–$300K per side.
- **FOAF/stablecoin pool on Radix DEX:** foundation contributes FOAF paired with Radix-native stablecoin. Target: $50K–$150K per side.

These numbers scale with total treasury size; the percentage of treasury committed to LPs matters more than the absolute dollar figures.

### FOAF secondary listings

Beyond DEX listings, the foundation may pursue centralized exchange listings over time:

- **Tier 3 CEXs (small, niche):** accessible early, minimal listing fees, introduces FOAF to crypto retail.
- **Tier 2 CEXs (mid-size):** accessible mid-Phase 2 to Phase 3 with meaningful volume and some liquidity provision.
- **Tier 1 CEXs (Coinbase, Binance, Kraken):** typically require significant liquidity, legal review, and market-making relationships. Long-term aspiration, not an early priority.

CEX listings broaden access but aren't essential — healthy DEX liquidity on Ethereum and Radix covers the vast majority of use cases.

### Cross-chain considerations

FOAF token exists on Ethereum (initial deployment for fundraising) and is planned to bridge to Radix. RHEO exists only on Radix. Consequences:

- **FOAF has Ethereum liquidity** on Uniswap or similar, serving fundraising and governance participation for Ethereum-based users.
- **RHEO stays on Radix** because it's purely a utility token for Radix-based operations. No reason to bridge it.
- **When FOAF bridges to Radix**, FOAF/XRD and FOAF/RHEO pairs become relevant on Radix DEXs. The foundation seeds those pools.
- **Bridge liquidity** (the lock-and-mint pool) needs its own depth to handle user flows between chains. Foundation treasury contribution may be required.
- **FOAF holders may sit on either chain.** Governance voting mechanisms must accommodate both — either by requiring bridging to vote, or by supporting cross-chain signal aggregation.

### Risks to FOAF liquidity

The foundation monitors and plans for:

- **Seed-round unlock cliff.** When early investors' FOAF becomes transferable, a concentrated sell may overwhelm liquidity. Design mitigation: seed round purchases include a vesting schedule (typical range: 12–24 month total vest with cliff plus monthly or quarterly linear unlocks thereafter). This spreads supply release over time rather than creating a single wall of tradeable tokens. Secondary mitigations: LP incentives to encourage holders to deploy unlocked FOAF as LP rather than selling, foundation LP depth sized to absorb sensible post-cliff selling volume.
- **Team vesting cliff.** Team FOAF allocation vests over 3 years per tokenomics (see [Tokenomics](./tokenomics.md)). Cliff is typically 12 months followed by monthly or quarterly linear unlocks. Smooths the team-side supply release just as seed vesting smooths the investor-side release.
- **Airdrop distribution pressure.** Airdrops may create short-term selling pressure from recipients without long-term commitment to the protocol. Mitigation: airdrop distribution staggered across cohorts and regions rather than all at once; possible vesting on larger airdrop allocations; clear messaging that encourages staking over selling.
- **Governance capture via accumulation.** Concentrated buying of FOAF could concentrate governance power. DAO design considerations (quadratic voting, delegation systems, voting caps per address) mitigate this.
- **rFOAF lock trap.** rFOAF has no early withdrawal — FOAF locked for a duration cannot be exited until the lock period elapses. This is a feature (it's what makes commitment real) but creates a genuine liquidity tradeoff for holders. Mitigations: lock duration is user-chosen, not mandated; minimum lock is 30 days so short-term commitment is accessible; rFOAF lockers can delegate voting and continue to receive RHEO during lock.

### Risks to RHEO liquidity

The foundation monitors and plans for:

- **rFOAF generation versus fee consumption imbalance.** If rFOAF positions generate RHEO faster than fees consume it, RHEO price declines; if faster consumption, RHEO price rises. Sustained imbalance degrades fee predictability and treasury planning.
- **LP withdrawal cascades.** Third-party LPs may withdraw during market stress or to chase yield elsewhere. Foundation-maintained minimum LP position prevents total liquidity collapse.
- **Exchange concentration risk.** If RHEO is primarily on one DEX and that DEX has problems (exploit, downtime, regulatory), RHEO liquidity vanishes. Target at least two active venues by mid-Phase 3.
- **Oracle manipulation.** Fee pricing depends on RHEO/fiat rate. An attacker manipulating RHEO price on a thin market could distort fee payments. Mitigations: TWAP pricing, multiple oracle sources, manipulation-resistant price feeds.

### Treasury composition implication

Treasury composition tables below should be read with these liquidity requirements in mind. Specifically:

- Phase 3+ treasury should include RHEO/XRD and RHEO/stablecoin LP positions as a distinct category (not double-counted against the underlying asset allocations).
- A portion of the XRD and stablecoin reserves is committed to LP positions rather than pure holdings. This is still treasury but is locked in smart contracts providing market function.
- Returns from LP fees flow back to treasury and may offset operational costs.

---

## Treasury Composition

Recommended composition at each phase, as percentage of total treasury value.

### Phase 1

| Asset | % | Purpose |
|---|---|---|
| Stablecoins (USDC/USDT/DAI) | 80% | Fiat operations, payroll, contractors |
| FOAF reserve | 15% | Team vesting pool, strategic holdings |
| ETH / WETH | 5% | Ethereum deployment prep |

### Phase 2

| Asset | % | Purpose |
|---|---|---|
| Stablecoins | 55% | Fiat operations |
| FOAF reserve | 15% | Strategic holdings, airdrop reserve |
| XRD | 15% | Accumulating ahead of Phase 3 |
| ETH / WETH | 10% | Ethereum contract ops, bridge |
| Bitcoin (optional) | 5% | Macro reserve |

### Phase 3+

| Asset | % | Purpose |
|---|---|---|
| XRD (mostly staked) | 30–40% | Operational reserve, sponsorship, fee settlement |
| Stablecoins | 20–25% | Fiat operations |
| RHEO LP positions (RHEO/XRD, RHEO/stablecoin) | 8–12% | RHEO market liquidity; returns from LP fees |
| FOAF LP positions (FOAF/XRD, FOAF/stablecoin) | 5–10% | FOAF market liquidity; seeded across Ethereum and Radix venues |
| FOAF reserve | 10–15% | Strategic holdings, airdrops |
| ETH / WETH | 5% | Bridge operations (lower post-migration) |
| Bitcoin (optional) | 5–10% | Macro reserve, uncorrelated with FOAF performance |
| Other | 0–5% | Opportunities, partnerships |

LP positions are counted separately because the underlying assets are locked in smart contracts and not freely spendable. A portion of XRD, stablecoin, and FOAF reserves effectively routes through LP positions rather than sitting as pure holdings. LP positions also generate ongoing fee revenue that returns to treasury.

### Why XRD becomes dominant in Phase 3+

Every protocol operation on Radix costs XRD. If the treasury holds insufficient XRD, every price spike in XRD raises operational costs proportionally. By holding XRD as a primary reserve — and staking it for yield — the foundation:

- Hedges against XRD price appreciation.
- Earns validator rewards (7–12% APY at current Radix rates).
- Pre-funds multi-year sponsorship runway.
- Avoids being a forced buyer during market stress.

### Why stablecoins remain essential

Fiat-denominated expenses (payroll, legal, hosting, contracts, marketing) don't go away. A significant stablecoin position prevents the treasury from being forced to sell appreciating assets (XRD, BTC, FOAF) at bad times to cover operational costs.

---

## Risk Management

### Stress scenarios

The treasury should be sized and composed to survive:

**XRD 3x price spike.** If XRD triples while revenue stays flat, the foundation's effective Radix fee costs triple. A sized-correctly XRD treasury (already holding XRD at pre-spike prices) absorbs this entirely.

**XRD 80% drawdown.** Treasury value declines, but operations continue because fiat-denominated expenses are covered by stablecoin reserves. Staking yields continue (paid in XRD, still worth something).

**Transaction volume 10x growth.** More XRD spent on sponsorship, but also presumably more protocol revenue. Treasury should have sufficient unstaked XRD buffer to handle short-term spikes before rebalancing.

**Extended crypto winter.** Revenue falls across all streams. Stablecoin runway of 18–24 months of operations ensures survival without forced token sales at market lows.

**FOAF token price collapse.** Doesn't affect operations directly (FOAF isn't used for operational expenses), but affects the foundation's ability to use FOAF for strategic purposes. Treasury held primarily in non-FOAF assets specifically to decouple from FOAF price.

**RHEO liquidity crisis.** If RHEO market depth becomes inadequate — third-party LPs withdraw, DEX experiences an exploit, exchange consolidation collapses — the foundation cannot efficiently convert RHEO fee revenue into operational currencies. Immediate operations continue because XRD and stablecoin reserves cover costs independently of RHEO conversion; however, ongoing revenue-to-operations flow is disrupted. Mitigations: foundation-maintained minimum LP position on primary pair prevents total collapse; multiple DEX venues reduce single-point-of-failure risk; stablecoin runway buffer ensures operations continue through recovery period. Recovery action: foundation increases LP incentives temporarily to restore depth.

**Staking-to-fee imbalance.** FOAF staking generates RHEO continuously; fees consume it. If generation consistently outpaces consumption, RHEO price declines, which raises the effective cost of fee payments relative to foundation revenue (though the user-facing fee stays constant in fiat terms). If consumption outpaces generation, RHEO price rises, increasing staking yields in fiat terms but potentially pricing out smaller fee payments. DAO-governed parameters (staking rate, fee rates, burn percentage) provide levers to rebalance. Foundation monitors the imbalance metric monthly.

### Hedging principles

1. **Match asset to liability.** Operational expenses in Radix are in XRD; hold XRD. Expenses in fiat are in fiat; hold stablecoins.
2. **Diversify substrate risk.** Don't hold 100% in any single asset or substrate. If Radix has a protocol incident, stablecoins and BTC protect the foundation.
3. **Stake for yield where safe.** XRD staking is a first-party network reward; BTC and stablecoins can earn yield on conservative venues if desired.
4. **Maintain liquidity.** A portion of every major holding must be immediately accessible. Don't stake or lock up everything.
5. **Pre-commit to rebalancing rules.** Quarterly rebalancing toward target allocations prevents emotional decisions during volatility.

---

## Governance

### Centralized phase (through Q3 2025)

Treasury controlled by founding team via multi-signature wallet (Gnosis Safe on Ethereum, or equivalent on Radix once deployed).

Required signatures for treasury transactions above a threshold (e.g., 2-of-3 for transactions over $10K, 3-of-3 for transactions over $100K or any move touching more than 10% of treasury).

### DAO transition (Q3 2025–Q4 2026)

Governance gradually transitions. Treasury moves from multi-sig to DAO-controlled contracts on Radix. Proposals require:

- Minimum rFOAF balance to submit proposal (prevents spam).
- 10% quorum of total rFOAF supply for validity.
- Simple majority for approval (configurable per proposal category).
- Time-lock for execution (typically 48 hours) allowing community review.

### Transparency

Regardless of phase:

- Treasury addresses public and auditable on-chain.
- Quarterly treasury reports published publicly.
- All transactions above a threshold documented with rationale.
- Annual independent financial review (not audit in a CPA sense, but independent review for transparency).

---

## Sustainability Math

### When does FOAF become self-sustaining?

Defining self-sustaining as "protocol revenue exceeds operational costs without needing additional token sales or external grants":

**Minimum viable self-sustaining level (rough estimate):**

Monthly operational cost: $35K–$50K (Phase 3 with growing team).

Required protocol revenue: same, or higher with buffer.

At 3% transaction fee and 30% treasury share: required trade volume = $35K ÷ 0.009 = $3.9M/month or about $47M/year in network-processed trade value.

That's a meaningful network. Not huge — 50 active cooperatives each processing ~$80K/year of trades would suffice — but not trivial to achieve.

**What gets the foundation there:**

- Growth through Phase 3 with cooperative acquisition as the primary metric.
- Subscription revenue supplements protocol fees, reducing the volume threshold.
- Treasury yields (XRD staking, possibly other) generate 5–10% of operational costs passively.
- Grants and partnerships reduce direct costs during growth.

**When does that happen?** Target: late Phase 3 to Phase 4 (2027+). Before that, foundation operates on seed round proceeds and strategic funding.

### Key metrics to watch

The foundation and DAO should track:

- **Monthly active cooperatives** — leading indicator of adoption.
- **Network-processed trade value** — directly drives fee revenue.
- **Treasury runway in months** — how long can operations continue without new funding.
- **XRD treasury in years of projected sponsorship cost** — hedge adequacy.
- **Protocol fee revenue as % of costs** — self-sustainability progress.
- **Per-transaction cost trends** — especially after Hyperscale arrival.

---

## When to Reassess Substrate

Foundational assumption: FOAF operates on Radix Babylon (then Hyperscale post-2027) for the foreseeable future. Own-L1 migration is on the table but not planned.

Reassessment triggers — conditions under which the foundation would formally evaluate migrating away from Radix:

1. **Radix XRD costs consume more than 30% of foundation revenue** sustainably. Indicates substrate dependence is structurally expensive.
2. **Radix protocol inadequate** for FOAF's needs (e.g., Hyperscale doesn't deliver, mobile SDK stays immature, oracle infrastructure insufficient).
3. **FOAF has validator-set feasibility** — 500+ credible independent rFOAF holders willing to operate validator nodes with proper security practices.
4. **Another substrate** offers materially better economics or capabilities that cannot be replicated by staying on Radix.

If none of these conditions emerge, FOAF stays on Radix. This is the expected outcome. The foundation does not pursue own-L1 as a goal; it keeps the option open via the substrate-agnostic protocol specifications described in the [technical architecture](../technical/architecture.md).

---

## Summary

- Treasury exists to fund multi-decade operations, hedge substrate cost volatility, support ecosystem growth, and transition to DAO control.
- Composition shifts across phases: stablecoin-heavy in Phase 1, XRD-heavy with LP positions in Phase 3+.
- Revenue diversifies across protocol fees, subscriptions, API access, marketplace fees, and grants.
- **Both FOAF and RHEO must be liquid.** RHEO liquidity allows protocol fees to fund operations. FOAF liquidity provides the exit path that makes locking FOAF into rFOAF (and thus the whole RHEO-generation mechanism) rational. Foundation seeds and maintains DEX liquidity across Ethereum (FOAF) and Radix (FOAF and RHEO) to ensure both markets function. rFOAF itself is non-transferable and doesn't require liquid markets.
- XRD staking on Radix generates passive yield that partially offsets operational costs.
- Self-sustainability target: late Phase 3 to Phase 4 at roughly $47M/year network-processed trade value.
- Own-L1 migration is a hypothetical option, not a planned outcome. Radix is the target substrate.
- Governance transitions from multi-sig to DAO control over Q3 2025–Q4 2026, with transparency maintained throughout.

For related strategic documents, see [Tokenomics](./tokenomics.md), [Fee Structure](./fee-structure.md), [DAO Transition](./dao-transition.md), [Technical Roadmap](../technical/roadmap.md), and [Node Operators](../technical/node-operators.md).
