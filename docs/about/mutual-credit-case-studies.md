# Mutual Credit Case Studies and Crisis-Economy Deployment

This document captures prior-art deployments of mutual credit systems and the lessons FOAF should carry forward when deploying outside Canada, particularly in communities currently or historically affected by monetary instability.

It exists because FOAF's structural fit for crisis economies is real — communities suffering hyperinflation, capital controls, or financial-system collapse are precisely where mutual credit shows empirical traction. But "structurally suited" is not the same as "deployable today." This document tracks what other projects have actually done, what worked, what didn't, and where FOAF's current build has gaps relative to what crisis-economy deployment requires.

## Long-running mutual credit institutions (WIR, Sardex)

Before any blockchain-era project, two institutional mutual credit systems demonstrated empirically that the model can run for decades alongside state currency without collapse. Both are essential precedents and the strongest counter to the standard "alternative currencies always fail" objection.

### WIR Bank (Switzerland, since 1934)

Founded in 1934 by Werner Zimmermann and Paul Enz during the Great Depression, when conventional credit had dried up. Awarded a banking license in 1936. Originally called the Wirtschaftsring-Genossenschaft (Economic Circle Cooperative). Has run continuously through WWII, postwar reconstruction, every Swiss recession, the 2008 financial crisis, and into the present. Started with 16 members; now serves roughly 62,000 Swiss businesses across hospitality, construction, manufacturing, retail, and professional services.

**Structural note worth being honest about:** WIR is often described as mutual credit but is structurally closer to a closed-loop regional currency with central credit issuance. New WIR francs (CHW) come into circulation when WIR Bank itself extends loans to members, backed by member-pledged assets. So it's a chartered bank running a complementary currency, not a pure bilateral credit network like FOAF or Trustlines. Different mechanism, same anti-collapse outcome.

**Why it's a load-bearing precedent for FOAF's argument:**

- **90+ years of continuous operation alongside state currency.** The strongest possible empirical refutation of "alternative currencies always fail" or "the state will shut it down."
- **Counter-cyclical behavior is documented.** James Stodder's research showed WIR usage spikes during recessions and contracts during booms — exactly the stabilizing role mutual credit is supposed to play. Academic evidence, not just claims.
- **The state has no quarrel with it.** Switzerland has not interfered in 90+ years. Demonstrates that running an alternative currency for B2B value circulation is structurally compatible with operating under state monetary authority and tax requirements.

**What it doesn't validate:** WIR doesn't validate the bilateral peer-to-peer credit model FOAF uses. It validates "alternative B2B currency systems can persist." Different but adjacent claim.

### Sardex (Sardinia, since 2010)

Founded by Giuseppe Littera, Gabriele Littera, and Carlo Mancosu — three unemployed graduates in post-2008-crisis Sardinia. Initially conceived in 2006, launched as Sardex s.r.l. in 2010 as a response to the local credit crunch and bankruptcy wave following the financial crisis. By 2017, transaction volume surpassed 212 million euro-equivalent units. Currently 4,000+ participating businesses, annual trade volumes near 50 million euros.

**Structural note:** Sardex is closer to bilateral mutual credit than WIR. Members extend credit to each other directly, euro-denominated but non-exchangeable with euro. Each firm starts at zero and earns Sardex by selling to other members. Mobile app and online banking interface; QR-code point-of-sale payments. Modern instance, modern UX.

**Why it's a load-bearing precedent for FOAF's argument:**

- **Modern (post-2008) instance of mutual credit working at regional scale.** Refutes "WIR is just a Swiss historical anomaly." The model can be re-instantiated in current conditions and grow substantively in 15 years.
- **Crisis-driven adoption.** Sardex explicitly emerged in response to a credit crunch, validating the empirical pattern that mutual credit usage spikes when conventional credit fails.
- **Regional B2B focus is the workable scope.** Both WIR and Sardex stay within a defined region and a B2B audience. They don't try to be a global consumer currency. The regional, institutional scope is part of what makes them durable.

**Cross-pattern observation about WIR + Sardex:** Both succeed by being institutional / chartered / regulated, regional, B2B-focused. Neither attempts pure peer-to-peer consumer mutual credit at unrestricted geographic scope. FOAF's design is more ambitious (P2P consumer, geographically open, eventually decentralized) — which means FOAF is doing something WIR/Sardex haven't proven can work, while still claiming the broader category as validated. Worth being honest about that distinction in copy.

**Critical design pattern from both: own unit, pegged 1:1 to host fiat, non-exchangeable.** WIR has CHW (Wir Franc), Sardex has Sardex — each is its own unit denominated equivalently to host fiat (CHF, EUR) at issuance but explicitly non-exchangeable. You can't walk into a bank with WIR or Sardex and walk out with national currency. This is structurally distinct from "denominating tabs in fiat" — and it's probably the cleanest pattern for FOAF to adopt as well.

The own-unit pattern matters for several reasons:

- **Closed-loop legibility.** "FOAF-credit pegged 1:1 to CAD but non-exchangeable" is a different (and clearer) story from "CAD-denominated tabs in a closed circuit." Regulators, users, and tax authorities all parse the first more cleanly.
- **Defends against "are you trying to be a currency" objections.** WIR and Sardex have run alongside state currency for 90+ and 16+ years without regulatory pushback partly because they're clearly NOT trying to be fiat. They're complementary instruments. FOAF tracking balances directly in CAD blurs that distinction.
- **Architectural option for unit-of-account swaps.** If balances are conceptually "FOAF-credit pegged to CAD at issue," then re-pegging to silver (the RHEO direction) is a clean unit-of-account migration. If balances are conceptually "CAD," re-pegging is a re-denomination of fiat-equivalent debt — much messier.
- **Tax treatment is identical either way.** CRA's IT-490 on barter applies regardless of whether the unit is "CAD" or "FOAF-credit-equivalent-to-CAD." The pattern doesn't change the tax obligation; it just makes the regulatory category obvious.

FOAF's protocol design already supports this — trustlines can carry whatever unit-of-account framing the implementation chooses. The current Rails MVP just tracks balances as raw CAD numbers because that was the simplest path for the first implementation. The own-unit-pegged-to-fiat framing is a labeling/conceptual choice that future implementations (Scrypto on Radix, alternative clients) can adopt without a redesign. WIR and Sardex are the empirical validation that the pattern works for decades.

## Trustlines Foundation deployments

The Trustlines Foundation ran three pilot deployments before the project largely went dormant. Each tells a different story.

### Venezuela

The founding insight was that small businesses in Venezuela had already begun issuing handmade paper IOUs with stamps because the cash system had broken down. Coins didn't exist for change. Paper notes were worth less than the printing cost. The informal IOU system was already running, just unreliably — paper gets lost, worn out, or forged.

Local business associations reached out to Trustlines because they wanted a more durable version of what they were already doing, not a new economic concept. Trustlines didn't introduce mutual credit to Venezuela; they digitized an existing practice.

The use case was business-to-business credit within associations, not consumer-to-consumer P2P. Trustlines funded local researchers to identify partners and use cases before deploying anything technical. The pilot moved slowly by software-launch standards but quickly by community-organizing standards.

### Germany — Maingold

The Maingold project ran for 2.5+ years in Frankfurt. It is a hybrid model: digital community currency backed by goods and services from participating local businesses, exchangeable to EUR for consumers. Different from pure peer-to-peer mutual credit — closer to a regional alternative-currency network with fiat compatibility.

Worth understanding as a model that mixed local circulation with fiat exchange. Local businesses spent Maingold to pay suppliers and accepted it from consumers, with EUR redemption available. The system had momentum partly because fiat compatibility lowered the activation energy for participation.

### Rwanda

Earliest stage when Trustlines was actively running pilots. The chapter leader spent significant time on local research before any technical deployment. The pattern: research, identify champion, identify use case, then technology. Reflects the cautious approach to entering new geographies that the Venezuela experience taught.

## VimbisoPay / Credex (Zimbabwe — closest direct comparable)

The most directly relevant case to FOAF is the Credex protocol and the VimbisoPay client running on it in Zimbabwe. Currently live in production, in a hyperinflation country, using credloops as a first-class primitive, with explicit secured/unsecured distinction. Existence proof that the architecture FOAF is building works in production in the use case FOAF talks about.

### What's running

- **Credex** is the protocol — a shared-ledger API. Open source TypeScript on GitHub (`Great-Sun-Group/credex-core`). Live at `mycredex.app`. Cloud-deployed (Docker, Terraform). Not blockchain — centralized server architecture.
- **VimbisoPay** is a client built on top of Credex — mobile app plus a WhatsApp chatbot. Maintained by VimbisoPay Africa.
- **Great Sun Financial** is another agent in the ecosystem.
- **Geographic deployment:** Zimbabwe, with WhatsApp as the primary user interface (Zimbabwe has roughly 44% of mobile internet usage on WhatsApp — meeting users where they already are).

### Mechanical structure (strikingly close to FOAF)

**Credloops as a first-class primitive.** From their docs: "Asset and liability pairs are automatically strung together into credloops wherever possible across the credex ecosystem, and when a credloop is found and cleared, every account in the loop will have an accounts payable invoice cleared against an equivalent accounts receivable invoice." Same primitive FOAF treats as central.

**Replacing sovereign money with shared-ledger entries.** From their docs: "members to replace the use of third party money or other debt instruments that are issued by an outside sovereign with accounting entries on a shared ledger that are backed only by the sovereign credit, assets, and value-producing capacities of the transacting members." Same thesis as FOAF.

**Secured vs. unsecured credex.** Two service categories:
- **Secured credex** — backed by real assets (currency, gold). Conceptually equivalent to silver-pegged RHEO in FOAF's roadmap.
- **Unsecured credex** — liquidity for credit-based economic growth, scaled by individual participants' risk/reward calculations. Equivalent to FOAF's mutual credit between trustlines.
- **Credcoin** — a third category mathematically linked to natural resource flows. FOAF doesn't have an analog; worth understanding as adjacent thinking.

**Multi-client ecosystem.** Credex is the protocol; VimbisoPay is one client, others can build. Same architectural direction FOAF is heading (protocol plus multiple apps, not protocol plus single official app).

**Agent model.** "Secured credex agents" (VimbisoPay, Great Sun Financial) are permitted to issue unrestricted secured credexes, with daily auditing of trust accounts. Different governance approach from FOAF's planned threshold-tier model, but worth understanding as a pattern.

### Architectural differences from FOAF

- **Not blockchain.** Centralized server. Same operator-failure risk as any SaaS. Could go dormant in the same way Trustlines did, and users would have on-server balances they couldn't easily port elsewhere.
- **WhatsApp as primary interface.** Lower-friction than a custom app. Major lesson for crisis-economy deployment — meeting users on the platform they already use beats getting them to install something new.
- **Cloud-deployed.** Standard SaaS fragility around maintenance and infra costs.
- **No off-chain bilateral architecture.** State lives on the centralized ledger, not on user devices. Less resilient to operator failure than FOAF's design.

### Lessons FOAF should carry forward

1. **WhatsApp / messenger interface for crisis-economy deployment.** Native apps assume a level of digital infrastructure that doesn't exist everywhere. WhatsApp is already on every relevant phone in Zimbabwe, Venezuela, Lebanon, etc. A messenger-based interface is significantly higher-leverage than asking people to install a new app. Worth considering as a deployment option distinct from the GrowOperative native app for non-Canadian rollouts.

2. **Multi-client by design, not as an afterthought.** Credex deliberately separates protocol from clients, so that a third party (VimbisoPay) can build a region-specific client without forking. FOAF's architecture should explicitly support this — open API surface, no privileged official-client paths, third-party clients welcome.

3. **Secured/unsecured distinction is a real pattern, not just a FOAF-specific idea.** Credex has it. FOAF's silver-pegged RHEO direction is the same shape. The dual-track design (real-asset-backed credit alongside pure mutual credit) shows up in production systems, not just in FOAF's design notes.

   Note: Credex's multi-denomination support (CXX, XAU, USD, CAD) is an implementation of the currency-network pattern Trustlines established years ago. FOAF can borrow the same pattern off the shelf when it's time to add multi-denomination — denomination-scoped trustlines, multi-hop within a denomination, optional cross-denomination at boundaries. Solved design problem; not yet shipped in FOAF.

4. **Production existence proof for hyperinflation use case.** Zimbabwe is a real ongoing hyperinflation context. The fact that mutual credit with credloops can run there in production means FOAF's "this works in crisis economies" thesis isn't aspirational — it's empirically validated by an actively-operating system.

5. **The centralized-server fragility we keep discussing applies here too.** Credex is open source, but the running deployment is a single SaaS instance on cloud infrastructure. If Great Sun Group stops maintaining `mycredex.app`, users with balances would face the same recovery problem Trustlines users did. FOAF's off-chain bilateral architecture is structurally more resilient than what Credex has built — that's a real differentiator if FOAF expands into the same problem space.

### Why this is the most relevant case study

Trustlines is dormant. BarterPay is centralized point-system, structurally different. Credex/VimbisoPay is a live, currently-operating mutual credit system using credloops as first-class primitives in a hyperinflation country. The architecture and use case overlap with FOAF substantially. If FOAF wants to deploy in similar contexts, this is the project to watch closely, learn from, and possibly partner with.

## BarterPay and Barter It (Canadian comparable)

Worth covering not as a mutual credit precedent but as a present-day comparable in the same problem space. Mechanically these are centralized point systems closer to a SaaS implementation of LETS than to mutual credit. Worth understanding because the audience overlap with FOAF is significant and the contrast clarifies what FOAF actually is.

### BarterPay (parent operation)

Founded by John Porter, Hamilton, Ontario. 25 years in barter payment. Positioned as a "social profit enterprise" (B-corp-style). Substantial operational track record:

- 4,000+ business members across 22 Canadian cities, plus 100 charities
- Claims $600M+ in barter transactions completed historically, $200M+ in claimed business savings
- CBC News coverage in 2018; Startup Canada COVID-recovery partnership in 2020
- Uses "trade dollars" as the unit of account; B2B-only

This is not a fragile startup. It's an established Canadian business that has weathered the 2008 crisis, the cryptocurrency boom and bust, and COVID, and is still operating.

### Barter It (consumer / P2P spinoff)

Launched within the last 3 years to address the demand from "everyday people" wanting access to the kind of bartering BarterPay offered businesses. Same founders, different audience and mechanism:

- Consumer / P2P web app
- Subscription-based participation
- Uses BITS as the internal point unit (separate from BarterPay's trade dollars)
- Branding: "freedom-loving Canadians" — explicitly courting the same sovereignty-leaning audience FOAF/GrowOperative targets through Telegram outreach
- Smaller scale than parent operation; subsidized by parent revenue

### Mechanical structure

BITS is a centralized point system, not a credit network:

- Central issuance and ledger controlled by Barter It / BarterPay
- Members earn BITS by selling, spend BITS by buying — single unit, no bilateral credit relationships
- No trust graph, no multi-hop routing, no credit loops to cancel
- Subscription required to participate — paywall on access to the network
- If the operator stops running it, BITS go to zero

In other words: BITS is essentially LETS reimagined as a SaaS product. Same structural mechanism (centralized point ledger, single unit, no credit relationships), different operator and business model.

### What this means for FOAF positioning

The naive "they could fail and you lose your balances" argument is weaker than it looks for Barter It specifically, because the parent operation (BarterPay) is established and could absorb or sustain Barter It if needed. Don't lead with operational risk as the differentiator — it's not the strongest framing.

The honest differentiators are mechanical:

- **Decentralized credit graph vs. centralized point ledger.** This is the actual difference, regardless of who has more runway.
- **No subscription, no paywall on participation.** Real difference, especially for low-income users and freedom-leaning audiences who object to gatekeepers.
- **Multi-hop routing through trust paths.** Not a feature gap on Barter It's part — a different mechanism. They couldn't easily add it.
- **Credit loops cancel debts without anyone moving cash or points.** Same.
- **Off-chain bilateral relationships survive operator failure.** Trustline state lives on user devices. Even if the FOAF Foundation went dormant, the bilateral relationship Robin and his neighbour built remains reconstructible.

### Audience overlap

Both projects court the same Canadian freedom-leaning, sovereignty-aware, prepper-adjacent audience. Telegram channels (Kootenay Preparedness Initiative, Kootenay Freedom Info Hub, etc.) have already shared Barter It links. Some overlap with the GrowOperative target user base is inevitable. The honest framing for that audience is "different shape of the same problem" rather than competitive positioning.

## Cross-cutting lessons from Trustlines

The pattern across all three deployments:

**Mutual credit deploys best when it formalizes existing informal economic relationships.** Don't introduce mutual credit to a community that doesn't have informal credit relationships already. Find communities where "running a tab," "the IOU notebook," "the gift economy," or "the LETS attempt" is already in motion, then formalize.

**Local champions matter more than technology.** Each deployment had a chapter leader doing research, identifying the right institutional partner (business association, cooperative, regional network), and adapting the use case to local context. Without that local presence, the deployment doesn't happen.

**Existing community institutions are the right organizing unit.** Random individuals can't be the unit of deployment. A business association, a local food cooperative, a municipal program, a religious community — these are the structures that successfully absorbed Trustlines. The FOAF analog: the Crawford Bay food network, the Kaslo community, future regional partners — communities with existing organizing structures, not flat lists of individuals.

**Use cases vary by context.** Bill splitting, time credits, gift vouchers, "People's ATM," community currencies, B2B trade credit. The use case has to fit local need. The food-economy framing that works in Crawford Bay doesn't translate to a Caracas business association issuing supplier credit.

**Crisis economies are the strongest fit.** Mutual credit usage peaks during high inflation and after financial crises. The 2008 financial crisis drove uptake; Venezuelan hyperinflation drove uptake. The empirical pattern validates the structural argument: mutual credit becomes valuable precisely when conventional money fails.

**Technology is necessary but not sufficient.** Trustlines spent significant time and grant funding on local research, partnerships, and adaptation per region. The technology was the easy part. The community-organizing was the slow part.

**Timeline reality.** Trustlines' Venezuela pilot took years from initial conversation to on-the-ground deployment. International expansion is multi-year, partnership-driven, and grant-funded. It is not a software release.

## Hyperinflation sniff test for FOAF

A walkthrough of what happens to GrowOperative if CAD goes 10x in three months and 100x over a year.

### What survives structurally (the protocol-level wins)

- **Bilateral credit relationships themselves.** Trust between counterparties isn't denominated in CAD. Hyperinflation doesn't dissolve it.
- **Credit loop closing.** "I owe you 100, you owe Sarah 100, Sarah owes me 100" cancels regardless of what 100 means. Loops close debts before the unit can be devalued. Stronger structural property than fiat systems have.
- **Trust graph topology.** Who knows whom and who's willing to extend credit doesn't depend on inflation.
- **Off-chain bilateral architecture.** Most of the system lives on devices, not on a central ledger. No central balance sheet to be inflated away.
- **FOAF and RHEO as non-fiat assets.** Token-denominated value isn't directly CAD-exposed. Foundation treasury in XRD or RHEO survives where CAD operating budget wouldn't.

### What breaks immediately (implementation gaps)

- **Existing CAD-denominated balances become a creditor-screwing mechanism.** "Robin owes neighbour $200 from two weeks ago" — settled at face value today, the neighbour takes a real loss. The system has no inflation adjustment. This is a real bug for crisis-economy deployment.
- **Credit limits in CAD become meaningless.** "Trust limit is $500 between us" is a meaningful constraint today and irrelevant in two months. Users have to manually renegotiate. No auto-adjusting limits.
- **Quoting and pricing UX collapses.** Multi-hop quotes calculated and stored at request time become stale before acceptance. The pricing fallback chain (UserRelationshipPrice → category default → global default) is all CAD-denominated.
- **Foundation runway in CAD evaporates.** Whatever fiat reserves exist lose 90%+ purchasing power.
- **Cash settlement leg is broken.** "Payer records amount, payee confirms" works as a primitive; the amount being CAD is the broken part.

### What strengthens (counter-cyclical)

- **Demand for the system goes up dramatically.** Hyperinflation actively recruits users. The Crawford Bay / Kaslo / regional resilience audience that's currently sympathetic becomes desperately invested.
- **Existing barter relationships matter more.** Social capital becomes more valuable in real terms.
- **Foundation treasury in XRD becomes a tailwind.** Non-fiat assets appreciate in CAD terms during fiat collapse.

### What gets caught flat-footed (the timing problem)

The silver-pegged RHEO unit-of-account swap is **designed but not built**. In a sudden currency event (peso-style overnight 50% devaluation), the system has no actual switchover capability. Users would be left renegotiating positions manually, switching to ad-hoc commodity-backed pricing in chat, operating without UI support for non-CAD denomination, and watching pre-event balances settle at face value (creditor losses) until they figure out the workaround.

In a slow-onset hyperinflation, there's time to engineer a unit-of-account swap. In a sudden event, no time.

### Pass/fail honest read

Pass on the structural primitives. Fail on the current implementation if a sudden event hits today. Pass with engineering effort if a slow-onset event gives 6-12 months to retrofit. The mutual credit thesis is correct; the build hasn't fully delivered on it yet.

## Implementation gaps for global / crisis-economy deployment

What FOAF's current build is missing for a Venezuela-equivalent deployment:

1. **Multi-currency / multi-denomination support per trustline.** Today: CAD only. Needed: USD, goods baskets, gold weight, hours of labor, local currency, whatever the local population trusts. Not just translation — actual unit-of-account flexibility per relationship.

2. **Inflation-adjustment primitive on existing balances.** Could be opt-in: "this trustline tracks balance in CAD with inflation adjustment indexed to [oracle]." Without this, all pre-event balances become creditor-loss events on settlement.

3. **Localization.** Language, cultural fit, payment patterns. Crawford Bay's food-share UX doesn't translate directly to a business-association credit-note system in Caracas.

4. **Smartphone-and-network resilience.** Trustlines deployed in Venezuela where electricity, internet, and smartphones aren't reliable. The off-chain bilateral architecture helps, but the current implementation assumes connectivity for sync. Crisis deployment needs longer offline-tolerance.

5. **Custody for non-crypto-native users.** Five Free FOAF custodial wallets are the right direction. For crisis-economy deployment, even simpler primitives are needed — paper-backup, SMS-recovery, business-association-administered accounts.

6. **Local partnership infrastructure.** Trustlines spent significant time and grant funding to find and equip local researchers and business associations. FOAF doesn't have that yet outside Crawford Bay.

7. **Chapter-leader pattern.** Trustlines' approach scales by recruiting and supporting local champions. FOAF's expansion plan should adopt the same — Kaslo champion, Nelson champion, eventually international champions, each running their region.

## Architectural advantages over Trustlines

Worth being honest about where FOAF improves on the precedent:

- **Off-chain bilateral architecture is more resilient than Trustlines' Ethereum-mainnet design.** Trustlines hit gas-cost problems for small transactions. FOAF on Radix Hyperscale plus off-chain bilateral solves that.
- **Optional on-chain settlement** lets users in crisis economies opt in to durable proof when they need it, without paying gas overhead for everyday trades.
- **Credit loops** were conceptually present in Trustlines but expensive on-chain. FOAF's design makes loop closing structurally cheap.

## Realistic timeline framing

Crisis-economy deployment is a 3-5 year arc, not a release milestone. The shape:

- Year 1: research and partnership identification with one or two communities. No technical deployment yet.
- Year 2: technical adaptation per local context (multi-currency, localization, custody primitives). Initial pilots with named partners.
- Year 3+: scaling within established communities, recruiting champions in adjacent communities, learning from what works.

This is the Trustlines pattern. The technology is the easy part. The community-organizing is the slow part. FOAF should plan accordingly when discussing international expansion in investor narrative, roadmap copy, or partnership conversations.

## How to use this document

This document is reference material for strategic conversations about international expansion, crisis-economy use cases, hyperinflation scenarios, comparison with prior mutual-credit projects, and partnership patterns. It does not describe shipped or imminent functionality — it describes the gap between FOAF's current state and what global crisis-economy deployment would require.

Update when: another mutual-credit project (LETS revival, Sardex, anything new) provides an additional case study; a real crisis-economy partnership opportunity arises; FOAF closes one of the implementation gaps listed above.
