# FOAF Team Vesting

This document defines the vesting structure for FOAF tokens allocated to the founding team, core contributors, and future hires under the Team & Advisors allocation (16% of total FOAF supply per [Tokenomics](./tokenomics.md)).

**This is a design document, not a legal contract.** Actual team agreements are separate legal documents that codify the principles here into binding terms. Before using this structure in signed agreements, it must be reviewed by legal counsel qualified in the relevant jurisdictions.

Target audience: team members, foundation board, advisors, legal counsel, prospective strategic investors, and future DAO voters who will inherit governance of this structure.

---

## Rationale

The FOAF protocol exists to build long-term infrastructure for cooperative economic resilience. Team vesting should reflect that timeline and reward actual progress toward the mission, not calendar time served.

Traditional time-based vesting (e.g., 3 or 4 years linear) is the industry default and has the advantage of predictability, but it has two weaknesses for a mission-driven infrastructure project:

1. It releases tokens regardless of whether the protocol is actually succeeding. A team that ships features but fails to drive adoption still vests fully on schedule.

2. It treats every month of the vesting period as equivalent, even though early months (pre-adoption, pre-market) carry very different risk and value creation than later months (post-adoption, network maturing).

Milestone-based vesting ties token unlocks to observable protocol success. The team earns tokens by delivering the results that make FOAF valuable, not by staying employed for a specified duration. This also sends a clear signal to investors, community, and future DAO voters that team compensation is aligned with protocol success.

The structure includes a time-based backstop to prevent perverse outcomes if the protocol stalls or milestones become obsolete due to pivots — but the backstop is long enough (6 years) that milestones remain the primary driver.

---

## Structure Overview

**Allocation:** 16% of total FOAF supply, or 4,000,000 FOAF, distributed across founding team and core contributors per allocations defined in individual team agreements.

**Grant start date:** the date the individual team member's agreement becomes effective.

**Vesting mechanism:** milestone-based with time-based backstop.

**Milestones:** five protocol-level milestones, each triggering a percentage of team tokens to vest for all team members simultaneously.

**Time-based backstop:** any tokens remaining unvested six years after grant date vest automatically, regardless of milestone status.

**Cliff:** no cliff on milestones themselves; milestones are binary and trigger vesting the moment they're met. However, individual team agreements may include a minimum tenure requirement (typically 6 months) below which no vesting occurs regardless of milestones, to prevent milestone-driven short-timers.

---

## The Five Milestones

Each milestone specifies a trigger condition, a percentage of team tokens unlocked on trigger, and a measurement methodology.

### Milestone 1: Market Available

**Percentage unlocked:** 15%

**Trigger:** all of the following conditions met simultaneously:

- FOAF token deployed as ERC-20 on Ethereum mainnet (or its successor L1 if migration has occurred).
- Token listed on at least one decentralized exchange accessible to the general public.
- Foundation-operated liquidity position active with minimum depth of $50,000 equivalent per side of a primary trading pair (e.g., FOAF/ETH or FOAF/stablecoin).
- Liquidity position time-locked for a minimum of 12 months to prevent rug-pull appearance.

**Rationale:** until FOAF can actually be traded, vested tokens have no exit path and no market value. No team member should receive vesting before this is true. This milestone also ensures the foundation has followed through on seeding the market rather than deferring it.

**Measurement:** on-chain observable. DEX listing verifiable via the DEX's documented pairs. LP position verifiable via the foundation's disclosed wallet addresses. Time-lock verifiable via the LP contract's configuration.

**Expected timing:** Phase 2, mid-to-late 2026.

### Milestone 2: User Adoption

**Percentage unlocked:** 15%

**Trigger:** any one of the following adoption thresholds met, measured over a 30-day trailing window:

- **1,000 verified unique users** with at least one active trustline to a distinct counterparty. ("Verified unique user" means passing whatever proof-of-personhood mechanism the foundation has adopted — phone verification at minimum, or cooperative membership verification.)
- **50 active cooperatives** using the protocol, where "active cooperative" means a registered entity with at least 10 verified unique members and at least one trustline executed in the trailing 30 days.

The OR conditions allow the protocol to hit the milestone through individual user growth or cooperative-scale growth, whichever reaches threshold first. Protocol success could come either way.

**Rationale:** token value depends on adoption. Without users, the protocol isn't generating value, and team tokens shouldn't unlock. This milestone ensures the team drives real adoption before earning a second vesting tranche.

**Anti-gaming:**

- Trustline requirement prevents bot farm registrations (bots would need to form social graph connections).
- Distinct counterparty requirement prevents single-user-multiple-accounts inflation.
- "Active cooperative" definition requires real membership and activity, not just a registered entity.
- 30-day trailing window requires sustained activity, not one-off peaks.

**Measurement:** on-chain observable (trustline count, counterparty diversity) combined with off-chain identity verification records. Foundation publishes monthly metrics dashboards showing progress toward thresholds.

**Expected timing:** Phase 3, late 2026 to mid 2027 depending on adoption velocity.

### Milestone 3: Transaction Volume

**Percentage unlocked:** 20%

**Trigger:** any one of the following transaction volume thresholds met:

- **$500,000 cumulative network-processed trade value** since protocol launch, with at least 100 distinct trading pairs having transacted.
- **$100,000 monthly network-processed trade value** sustained for 3 consecutive months, with at least 50 distinct trading pairs each month.

Both thresholds include the distinct-trading-pairs requirement to prevent wash trading by controlled accounts.

**Rationale:** registered users who don't transact aren't creating real economic value. Volume milestones require that the protocol is actually being used for trade, not just signups. This differentiates "lots of signups" (cheap) from "real economic activity" (hard and valuable).

**Anti-gaming:**

- Distinct trading pair requirement prevents concentration (10 users each trading with each other 10 times is 10 pairs, not 100 transactions; volume between same pair repeatedly doesn't count toward diversity).
- Cumulative + sustained monthly alternatives prevent one-time volume spikes from qualifying.
- Trading pair distinctness measured across directed edges — A→B and B→A count as the same pair.

**Measurement:** on-chain for Phase 3+ deployments. For Phase 2 Rails-based trading, measurement via the operations table and foundation-maintained analytics. Foundation publishes monthly transparency reports.

**Expected timing:** Phase 3 to early Phase 4, mid 2027 to early 2028 depending on adoption.

### Milestone 4: Protocol Sustainability

**Percentage unlocked:** 25%

**Trigger:** protocol revenue (from fees and subscriptions, measured in fiat-equivalent terms) covers **at least 50% of the foundation's monthly operating burn for 6 consecutive months**.

**Rationale:** this is the financial inflection point where FOAF is on a path to self-sustainability. Before this milestone, the foundation depends on token sale proceeds and grants; after it, protocol revenue is structurally meaningful. Rewarding this milestone recognizes the team has built something that generates real value and can survive without continued external funding.

**Calculation:** monthly operating burn averaged over the preceding 6 months, compared to protocol revenue (fees received to treasury plus subscription revenue plus API revenue) over the same 6 months. The ratio must be at least 50% each month for all 6 months, not 50% averaged across the period.

**Anti-gaming:**

- Sustained 6-month requirement prevents a one-time revenue spike from qualifying.
- Revenue categories defined in advance (protocol fees, subscriptions, API, marketplace, grants explicitly excluded from the definition).
- Independent audit of revenue and burn figures at milestone trigger for verification.

**Measurement:** foundation financial records, audited annually and reviewed at milestone trigger event. Treasury transactions are on-chain and transparent; fiat-denominated figures come from audited foundation accounting.

**Expected timing:** late Phase 3 to Phase 4, 2027-2028 depending on adoption trajectory.

### Milestone 5: DAO Transition

**Percentage unlocked:** 25%

**Trigger:** all of the following conditions met:

- Foundation treasury has transitioned to DAO control (multi-sig replaced by DAO-governed smart contracts).
- DAO has executed at least **10 governance proposals** through its governance process, demonstrating that the governance system functions in practice.
- At least **one DAO-driven parameter change** (e.g., fee rate adjustment, routing premium change) has been executed, demonstrating active governance over protocol parameters.
- Foundation has formally transitioned to a minority role (foundation multi-sig holds less than 20% of governance weight, or foundation has explicitly stepped back from executive decision-making).

**Rationale:** the final vesting tranche rewards completing the transition to decentralized governance — the aspiration of the entire FOAF project. Without this milestone, FOAF remains a foundation-controlled protocol. Tying 25% of team vesting to DAO transition ensures the team has incentive to actually complete it rather than remaining centralized indefinitely.

**Anti-gaming:**

- Multiple conditions must all be met, not just one.
- Requires real governance activity (10 proposals executed), not just deployment of a governance contract.
- Foundation minority role requirement prevents "technically decentralized" but effectively centralized outcomes.

**Measurement:** on-chain observable. DAO treasury ownership verifiable on Radix; governance proposal executions verifiable in DAO contract state; foundation's governance weight verifiable by sum of foundation-controlled addresses.

**Expected timing:** Phase 4, 2027-2028 per the [DAO Transition](./dao-transition.md) roadmap.

---

## Summary Table

| Milestone | Unlock | Trigger (condensed) | Expected timing |
|---|---|---|---|
| 1. Market Available | 15% | FOAF tradeable, LP ≥ $50K/side | Mid-late 2026 |
| 2. User Adoption | 15% | 1,000 users or 50 co-ops active | Late 2026 – mid 2027 |
| 3. Transaction Volume | 20% | $500K cumulative or $100K/mo sustained | Mid 2027 – early 2028 |
| 4. Sustainability | 25% | Revenue ≥ 50% of burn for 6 consecutive months | 2027 – 2028 |
| 5. DAO Transition | 25% | DAO treasury control, 10 proposals executed, foundation minority | 2027 – 2028 |
| **Total** | **100%** | | |

**Time-based backstop:** any tokens remaining unvested 6 years after grant date vest automatically, regardless of milestone status. This caps the worst-case scenario at a 6-year waiting period and prevents team members from being trapped indefinitely.

---

## Measurement and Verification

Vesting depends on milestones being objectively verifiable. The foundation commits to transparent measurement processes:

### Monthly metrics dashboard

Foundation publishes a monthly metrics dashboard showing:

- Current progress toward each pending milestone.
- User counts, trustline counts, trading pair counts, cumulative and monthly volume.
- Foundation operating burn and protocol revenue with revenue/burn ratio.
- DAO governance activity (proposals executed, treasury status, foundation governance weight).

Dashboard methodology is documented and unchanging — moving the goalposts mid-flight undermines the entire structure.

### Milestone trigger events

When a milestone appears to be met:

1. Foundation publishes a milestone trigger notice with supporting data.
2. A 30-day community review period follows. Any community member can raise concerns about the measurement.
3. If no unresolved concerns, milestone is officially triggered and vesting occurs.
4. If concerns are raised, an independent review (external auditor or advisor committee) resolves the question before vesting.

### Disputes

If the community or any stakeholder disputes whether a milestone has been met:

- During centralized phase: foundation board makes final determination, informed by independent review.
- During DAO phase: DAO vote makes final determination.

Dispute resolution decisions are documented and published.

---

## Edge Cases

### Departure before full vesting

If a team member leaves before full vesting:

**Voluntary departure:** team member retains tokens vested at milestones triggered before departure date. Unvested tokens linked to unmet milestones are forfeited back to the team allocation pool.

**Termination for cause:** team member retains tokens vested at milestones triggered before termination date. Unvested tokens are forfeited back to the team allocation pool. Forfeited tokens remain available for future team members or DAO-directed redistribution.

**Termination without cause:** team member retains tokens vested at milestones triggered before termination date. Additionally, team member retains eligibility for milestones triggered within 12 months after departure date (acknowledging that their prior work contributed to those milestones being achievable).

**Disability or death:** remaining unvested tokens vest according to the time-based backstop but applied pro-rata from grant date to backstop date, regardless of milestone status. This is a compassionate provision.

**Milestone triggered during notice period:** standard milestone vesting applies; team member receives the unlocked percentage.

### Milestones triggered out of order

Milestones can be triggered in any order. Each milestone is independent; triggering Milestone 3 before Milestone 2 is possible and does not affect Milestone 2's future triggering.

### Milestones unlikely or impossible to reach

If a milestone becomes unreachable due to protocol pivot, scope change, or external event:

- During centralized phase: foundation board may propose amended milestones; amendment requires 2/3 board vote and team agreement.
- During DAO phase: DAO vote amends milestones; amendment requires supermajority (e.g., 66% or higher) to prevent gaming.

Amendments may not reduce the total percentage unlocked across all milestones (still 100%) but may modify individual milestone thresholds if genuinely warranted.

### Protocol forks or migrations

If the FOAF protocol forks or migrates to a different substrate:

- Team vesting rights follow the "official" protocol as determined by foundation or DAO governance.
- If team member holds both forks' governance/token positions, the vesting structure applies to the official fork only.

### Time-based backstop interaction with milestones

The 6-year backstop unlocks all remaining unvested tokens at once. If some milestones have been met in the meantime, only the unvested portion unlocks. The backstop does not retroactively redistribute already-vested tokens.

---

## Tax and Legal Considerations

**This section must be reviewed by qualified legal counsel before any team agreements are executed.**

### Vesting event taxation

In most jurisdictions, token vesting events create taxable events at the fair market value of tokens on the vesting date. Milestone-based vesting can create concentrated tax events (large chunks unlocking at a single moment) that may surprise team members with significant tax liabilities.

Mitigations team members should consider:

- Withholding or selling a portion of vested tokens at vesting to cover tax liability (foundation may offer a structured sell-to-cover facility).
- Individual tax planning with qualified professionals.
- 83(b)-style elections in US jurisdictions where available (elect to be taxed at grant rather than vesting, if permitted).

### Securities law classification

FOAF tokens' classification (security vs. utility vs. commodity) varies by jurisdiction and may be unclear during early phases. Team agreements should acknowledge this uncertainty and the team member's responsibility for compliance with applicable laws.

### Employment law interaction

Some jurisdictions treat token compensation as wages subject to employment law protections; others do not. Team agreements should be structured to comply with the relevant jurisdiction's employment law framework.

### Jurisdictional complications

Team members in different jurisdictions face different tax and legal regimes. The foundation may maintain multiple agreement templates optimized for different jurisdictions, all implementing the same underlying vesting logic but complying with local law.

---

## Governance of This Structure

### During centralized phase

Foundation board governs milestone definitions, measurement methodology, and dispute resolution. Amendments require 2/3 board vote and majority team agreement.

### During DAO transition

As DAO takes control, governance of vesting structure transitions. By DAO Phase (Milestone 5 trigger), the DAO has authority over:

- Amending milestone definitions (supermajority required).
- Resolving disputes.
- Redistributing forfeited tokens.

### Amendments to this structure

This document may be amended to improve clarity, fix errors, or respond to changed circumstances. Amendments may not:

- Reduce the total percentage of team tokens allocated (still 16% of 25M = 4M).
- Reduce the total vesting unlock across all milestones (still 100%).
- Retroactively require a team member to meet new conditions for already-triggered milestones.

Amendments may:

- Modify specific milestone thresholds with proper governance.
- Clarify measurement methodology.
- Adjust time backstops with appropriate notice.
- Update dispute resolution processes.

---

## Example Scenarios

### Scenario 1: Happy path

Team member joins at foundation inception with 100,000 FOAF allocation.

- Month 8 (Phase 2): Milestone 1 hit. 15,000 FOAF vest.
- Month 18 (Phase 3): Milestone 2 hit. 15,000 FOAF vest.
- Month 28: Milestone 3 hit. 20,000 FOAF vest.
- Month 36: Milestone 4 hit. 25,000 FOAF vest.
- Month 42: Milestone 5 hit. 25,000 FOAF vest.
- Full vesting in 3.5 years, entirely driven by protocol milestones.

### Scenario 2: Slower path

- Months 1-10: no milestones hit. Zero vested.
- Month 12: Milestone 1 hit. 15,000 FOAF vest.
- Month 30: Milestone 2 hit. 15,000 FOAF vest.
- Month 48: Milestone 3 hit. 20,000 FOAF vest.
- Months 48-72: Milestones 4 and 5 not yet triggered.
- Month 72 (6 years): time-based backstop activates. Remaining 50,000 FOAF vest automatically.
- Full vesting at 6 years despite two milestones never triggering.

### Scenario 3: Departure midway

Team member joins with 100,000 FOAF. Milestones 1 and 2 have triggered (30,000 FOAF vested). Team member voluntarily departs at month 20.

- Team member retains 30,000 FOAF from milestones already triggered.
- Remaining 70,000 FOAF forfeit back to team allocation pool.
- If team member had been terminated without cause and Milestone 3 triggered at month 25, they would have received the additional 20,000 FOAF (since it triggered within 12 months of termination).

### Scenario 4: Milestone dispute

Foundation claims Milestone 2 triggered based on adoption metrics. Community review period raises concerns that 200 of the 1,000 users are controlled by a single operator (proof-of-personhood failed).

- Foundation engages independent auditor to verify user uniqueness.
- If auditor confirms 800 unique users, milestone is not yet met. Foundation continues measuring.
- If auditor confirms 1,050 unique users after excluding duplicates, milestone is confirmed triggered (still above threshold).
- Decision is published with supporting data.

---

## Relationship to Other Documents

This document operates alongside:

- [Tokenomics](./tokenomics.md) — defines the 16% team allocation being vested under this structure.
- [Governance](./governance.md) — defines rFOAF, the locked-commitment position that team FOAF is recommended to be locked into upon vesting. Strong recommendation: team members lock their vested FOAF into rFOAF at maximum duration as a signal of long-term commitment to the network.
- [Treasury and Operations](./treasury-and-operations.md) — vesting schedule affects foundation's tradeable FOAF supply and LP planning.
- [DAO Transition](./dao-transition.md) — Milestone 5 depends on DAO transition completion per that document's timeline.
- [Fee Structure](./fee-structure.md) — Milestone 4 (sustainability) depends on fee revenue defined there.
- [Funding / Seed Round](../funding/seed-round.md) — seed round vesting is separate from team vesting but should be coordinated for consistency.
