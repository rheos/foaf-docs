# FOAF Governance

This document defines how FOAF governance works at the mechanical level — how holders commit to the network, how voting operates, and how decisions are made. It complements [DAO Transition](./dao-transition.md), which covers the timeline for transitioning governance from foundation to DAO control.

**This is a design document, not a legal or operational constitution.** The mechanisms described here are codified through on-chain smart contracts (once deployed on Radix in Phase 3) and community-adopted processes. Before deployment, critical parameters should be reviewed by legal counsel and security auditors.

---

## Two-Tier Staking System

FOAF governance uses a dual staking system that accommodates different levels of commitment and participation:

### vFOAF (Vote-Escrowed FOAF) - Simple Staking

**vFOAF** represents basic network participation. Users stake FOAF tokens and receive vFOAF instantly with full flexibility.

**Key Features:**
- **1:1 ratio** - 100 FOAF staked = 100 vFOAF
- **No time lock** - unstake anytime
- **Immediate access** - voting rights and RHEO generation start immediately
- **Standard rewards** - base rate RHEO generation, basic voting weight

**Target Users:** New participants, casual users, those wanting flexibility

### rFOAF (Rooted FOAF) - Commitment Staking

**rFOAF** represents deep commitment to the network through time-locked staking with enhanced rewards.

**Key Features:**
- **Enhanced multiplier** - up to 4x voting weight based on lock duration
- **Higher RHEO yield** - 1.5x to 3x generation rate
- **Protocol revenue share** - exclusive access to treasury distributions
- **Time commitment** - 6 months to 2+ years lock duration

### Comparison: vFOAF vs rFOAF

| Feature | vFOAF (Simple) | rFOAF (Commitment) |
|---|---|---|
| **Staking** | Instant, 1:1 ratio | Time-locked, multiplier based |
| **Flexibility** | Unstake anytime | 6 months to 2+ years lock |
| **Voting Weight** | 1x (1 FOAF = 1 vote) | 1.5x to 4x based on lock |
| **RHEO Generation** | Standard rate | 1.5x to 3x enhanced rate |
| **Revenue Share** | None | Yes - protocol revenue distributions |
| **Target Users** | New users, flexibility seekers | Core community, long-term believers |

### Progressive Participation Path

Users naturally progress from vFOAF to rFOAF as they learn and commit:

1. **Entry:** Receive vFOAF through airdrops (immediate participation)
2. **Learning:** Experience governance and RHEO generation
3. **Commitment:** Convert some vFOAF to rFOAF for better rewards
4. **Leadership:** Core participants with mostly rFOAF positions

### How rFOAF Multiplier Works

rFOAF uses time-weighted commitment to calculate voting power and rewards:

```
rFOAF_multiplier = 1 + 3 × (time_remaining / max_lock_duration)
```

Examples:
- 100 FOAF locked for 2 years = 400 rFOAF voting weight (4x multiplier)
- 100 FOAF locked for 1 year = 250 rFOAF voting weight (2.5x multiplier) 
- 100 FOAF locked for 6 months = 175 rFOAF voting weight (1.75x multiplier)

rFOAF decays linearly as time remaining decreases, incentivizing lock extensions.

### Staking Parameters

| Parameter | vFOAF | rFOAF |
|---|---|---|
| **Minimum stake** | 1 FOAF | 100 FOAF |
| **Lock duration** | None (flexible) | 6 months to 2 years |
| **Early withdrawal** | Anytime | Not permitted |
| **Voting weight** | 1x | 1.5x to 4x |
| **RHEO generation** | 1x base rate | 1.5x to 3x enhanced |
| **Revenue share** | No | Yes |
| **Transferability** | Non-transferable | Non-transferable |

### What rFOAF unlocks

**Voting rights** — rFOAF balance is your voting weight in DAO governance. Standard delegation supported: holders can delegate their voting rights to trusted delegates without unlocking their FOAF. Snapshot voting: each proposal captures rFOAF balances at a specified block (typically 7 days before vote opens) to prevent last-minute manipulation.

**RHEO generation** — rFOAF holders earn RHEO at a continuous rate proportional to their rFOAF balance. RHEO is the fee payment rail that flows through trust paths (see [Fee Structure](./fee-structure.md)). The foundation's RHEO generation rate is calibrated by DAO-governed parameters.

**Protocol revenue share** — rFOAF holders collectively receive a portion of the protocol revenue directed to rFOAF stakers. Distribution mechanism: weekly or monthly pro-rata distribution of accumulated revenue, denominated in whatever token(s) the revenue arrives in (primarily RHEO, sometimes XRD or stablecoins).

### Why rFOAF instead of simple holder voting

**Attack resistance.** If governance were based on simple FOAF holding, an attacker could acquire a large FOAF position via flash loan, vote on a malicious proposal, and exit — all within a single transaction. rFOAF's lock requirement prevents this: voting power depends on a committed position that cannot be instantly acquired or liquidated.

**Alignment.** rFOAF holders have their capital committed to the network for a duration. If the network fails, they lose. This aligns governance incentives with network success far more directly than pure holder voting.

**Mission coherence.** FOAF is about cooperative economics and trust-based systems. Governance by people who have made commitments (locked their capital) fits this philosophy; governance by arbitrary holders who might be speculators does not.

**Capital efficiency.** rFOAF unifies three mechanisms (staking for RHEO, governance voting, revenue sharing) into a single position. Users don't manage three separate commitments; one lock does it all.

---

## Threshold-tiered voting (design direction under consideration)

The stake-weighted voting described above is the original design. We are actively considering replacing it with a threshold-tiered cooperative model that aligns better with the foundation's mission and reduces legal exposure.

The core insight: separate the two reasons to hold FOAF.

**Operational capacity** (more FOAF = more RHEO generation = more ability to back transactions in your network) scales linearly with holdings. Unbounded. This is the "patronage" reason to acquire FOAF, and the more activity you generate, the more you reasonably want.

**Governance weight** is capped per qualifying account. Stake determines which tiers of decisions you qualify to vote on, not how loud your voice is within a tier. Each qualifying account gets one vote per qualifying tier.

This separation maps onto traditional cooperative law: returns scale with patronage (how much you use the network), control does not scale with capital. Co-ops are not securities specifically because of this distinction.

### Tier structure (illustrative)

| Tier | Decision type | Required rFOAF |
|---|---|---|
| 0 | Minor proposals, signaling, comments | Any FOAF holder |
| 1 | Community programs, ambassador budgets, regional grants | 10+ rFOAF |
| 2 | Parameter changes within established ranges | 100+ rFOAF |
| 3 | Treasury moves, fee structure, governance mechanics | 1,000+ rFOAF |
| 4 | Constitutional changes, protocol upgrades | 10,000+ rFOAF |

At each tier, every qualifying account casts one vote. The threshold is qualification, not weight.

Specific thresholds will be calibrated to circulating rFOAF supply and expected participant numbers. The structure is the load-bearing element, not the exact numbers.

### Why this is sybil-resistant

Splitting wallets to multiply votes has push-pull pressure built in.

If you have 1,000 FOAF and split it into 100 wallets of 10 each, you can now cast 100 votes on Tier 1 decisions. But you cast zero votes on Tier 2-4 decisions because no individual wallet meets the higher thresholds. To influence high-stakes decisions, you have to consolidate. Whoever wants real protocol influence faces a choice: many low-tier votes or one high-tier vote. They cannot have both.

The mechanism is also self-balancing because rFOAF requires time-lock commitment. Sybil-splitting becomes expensive when all 100 sybil wallets need to time-lock their stake for years to qualify for higher tiers.

Reactive sybil management (community challenges, anomaly detection, KYC at the highest tiers) handles edge cases on top of the structural defense.

### Implications for the existing rFOAF revenue share

The existing design distributes protocol revenue pro-rata to rFOAF holders, sometimes denominated in stablecoins or XRD. This is dividend-shaped and creates the strongest possible Howey exposure. Under the threshold-tiered direction, that distribution is replaced by:

- **Burn-based deflation** as the primary mechanism for returning value to holders. Fees burn RHEO (or, in the long run, partially burn FOAF), creating supply pressure that benefits all holders without a direct payment.
- **Active-participation gates** for any direct revenue routed to holders. If revenue does flow to participants, it routes only to those who voted on a meaningful share of proposals in the period — making it explicitly compensation for governance work, not passive income.

### What this gives up

Speculative passive demand for FOAF is reduced. Buying FOAF does not increase your governance leverage; it only increases your operational capacity and qualification level. People who buy FOAF for "passive yield" or "governance influence proportional to capital" find no purchase here.

This is intentional. That class of demand is the most legally exposed and the most misaligned with the cooperative mission. The remaining demand (operators, heavy users, generous network members, governance-active participants, subnet treasuries) is exactly the demand that aligns with how the network is meant to operate.

### Status

This is design thinking, not committed protocol. The threshold-tiered model is being weighed against the original stake-weighted design. The original design above remains documented because:

1. The decision is not final
2. Some elements (rFOAF time-lock for governance access, council structure, proposal lifecycle) carry over either way
3. The choice has implications across tokenomics, fundraising narrative, and legal posture that need to be settled together

Final design will be locked in before the protocol moves to Phase 3 (Radix Babylon deployment), since that's when on-chain governance contracts get written.

---

## Governance Mechanics

### Proposal lifecycle

**1. Draft.** Any FOAF-ecosystem participant can draft a proposal in the community forum. Drafts are discussed publicly before moving to formal submission.

**2. Submission.** To submit a formal proposal for vote, the proposer must hold a minimum rFOAF balance (the *proposal threshold*). Initially: 50,000 rFOAF. This threshold can be adjusted by DAO vote.

**3. Review period.** Once submitted, proposals enter a minimum 7-day review period during which the community can discuss, propose amendments, or identify issues.

**4. Snapshot.** At the end of the review period, a snapshot is taken of all rFOAF balances. This snapshot determines voting weights for this proposal; subsequent locking or unlocking doesn't affect this vote.

**5. Voting period.** A minimum 5-day voting window during which rFOAF holders cast votes (for, against, abstain). Votes can be changed until the window closes.

**6. Quorum and approval.** For the proposal to pass, both conditions must be met:
 - **Quorum:** total participating vote weight ≥ 10% of total rFOAF supply.
 - **Approval:** supermajority of weighted votes in favor, typically 50% + 1 (or higher for specific categories — see Proposal Categories below).

**7. Execution timelock.** Approved proposals don't execute immediately. A 48-hour timelock allows the community to review the decision and, if something has gone wrong (critical flaw discovered, governance attack detected), a final security review vote can cancel execution.

**8. Execution.** After timelock, the proposal executes: smart contract calls are made, treasury movements occur, parameter changes activate.

### Proposal categories

Different types of proposals have different approval thresholds:

**Standard proposals (50% + 1):** protocol parameter changes within established ranges, treasury grants, ecosystem funding decisions, partner approvals. Normal governance.

**High-stakes proposals (66% + 1):** changes to fee structure, changes to rFOAF mechanics, treasury asset allocation changes exceeding 10% of treasury, governance mechanism changes.

**Critical proposals (75% + 1 and extended timelock):** protocol upgrades, substrate migrations, changes to token supply mechanics, modifications to vesting structures.

**Emergency proposals (5 of 7 council signatures + 51% vote):** responses to active security incidents. Bypasses normal timelocks but requires both technical council approval and community vote.

### Governance council

During early phases (through Phase 3), a 7-person governance council provides operational continuity:

- Initially composed of foundation team members and external advisors.
- Transitions to elected seats (DAO votes) over Phase 3–4.
- Responsible for technical review of proposals, emergency response, and operational decisions between governance votes.
- Cannot override DAO decisions, only respond to operational needs.
- Council members elected for 12-month terms with term limits.

Council is an operational body, not a governance body. Its role is to execute, not to decide. All substantive decisions go to DAO vote.

### Delegation

rFOAF holders can delegate their voting rights to a chosen delegate. Delegation:

- Transfers voting rights only; does not transfer rFOAF itself.
- Can be revoked at any time, taking effect immediately (or at the next snapshot for active votes).
- Allows delegation to any address, including identified community members, multi-sigs, or delegate DAOs.
- Is encouraged for holders who don't actively follow governance but want to participate through trusted representatives.

Foundation maintains a public delegate registry where candidates can publish their positions and track records. Community members can choose delegates based on published positions.

---

## Voting Rights Across FOAF Allocations

Different FOAF allocations have different relationships to governance:

### Seed round participants

- FOAF subject to vesting schedule.
- Vested FOAF can be locked into rFOAF and participate in governance.
- Unvested FOAF holds no governance weight (cannot be locked while unvested).

### Team and advisors

- FOAF subject to milestone-based vesting (see [Team Vesting](./team-vesting.md)).
- Vested FOAF can be locked into rFOAF.
- Strong recommendation: team FOAF is immediately locked into rFOAF upon vesting, at maximum lock duration, as a signal of commitment. Individual team members ultimately decide their own locking strategy.

### Community airdrops

- Airdropped FOAF is freely transferable.
- Recipients choose whether to lock into rFOAF.
- Airdrop campaigns may include LP or lock-matching incentives to encourage conversion to rFOAF.

### Node operators

- Tokens earned through node operations vest per an established schedule.
- Vested tokens can be locked into rFOAF.
- Node operators may be required to maintain a minimum rFOAF balance as part of their operator role (details in [Node Operators](../technical/node-operators.md)).

### Treasury and DAO grants

- FOAF held in treasury has no direct governance weight (the DAO doesn't vote with its own treasury).
- Treasury tokens distributed via grants or programs vest per specific terms and become eligible for rFOAF locking when vested.

### Liquidity provision

- FOAF held in LP positions is not directly locked into rFOAF and does not have voting rights.
- Some protocols create mechanisms to preserve voting rights for LP'd tokens; FOAF may adopt this in future via DAO vote, but initially LP and rFOAF are separate decisions.

---

## Quorum and Participation

Healthy governance requires participation. Mechanisms to encourage it:

**Quorum thresholds.** Proposals require 10% of rFOAF supply participating for validity. If quorum isn't reached, proposal fails and must be resubmitted. This prevents small cabals from passing proposals with minimal community input.

**Delegation incentives.** Delegates who attract significant delegated vote weight may earn a small portion of protocol revenue as compensation, encouraging active, informed delegation.

**Voting rewards.** rFOAF holders who consistently participate in governance (voting on a high percentage of proposals) may receive minor bonus RHEO distributions. Avoids making voting *required* but rewards participation.

**Absentee transparency.** Public dashboards show participation rates per delegate and overall. Holders can see whether their delegate is actively voting; delegates with poor participation can be revoked.

---

## Protocol-Level Parameters (DAO-Governable)

The following parameters are subject to governance votes once the DAO is active:

| Parameter | Initial value | Governance threshold |
|---|---|---|
| Transaction fee rate | 0% (Phase 1), TBD (post-activation) | High-stakes |
| Markup fee rate | 0% (Phase 1), TBD | High-stakes |
| Routing premium rate | 0% (Phase 1), TBD | High-stakes |
| Fee distribution (node operators / treasury / burn) | 50% / 30% / 20% | High-stakes |
| rFOAF revenue share allocation | 15% of treasury share (estimated) | High-stakes |
| Proposal threshold (rFOAF required to submit) | 50,000 rFOAF | Standard |
| Quorum percentage | 10% | Standard |
| Default approval threshold | 50% + 1 | Standard |
| Maximum rFOAF lock duration | 2 years initially | High-stakes |
| RHEO generation rate per rFOAF | Initially set, adjustable | Standard |
| Max hop count for multi-hop transfers | 5 | Standard |
| Timelock duration | 48 hours | High-stakes |

All of these are initial values; each can be modified through appropriate governance procedures.

---

## Emergency Governance

Situations requiring immediate action despite normal governance timelines:

**Active security incidents.** Exploits, critical bugs, attacks in progress. Governance council can propose emergency responses with reduced timelocks; requires 5 of 7 council signatures plus a rapid (24-hour) community vote with 51% approval.

**Substrate failures.** If Radix or bridge infrastructure experiences critical failures affecting protocol function, council can coordinate emergency response and substrate migration discussions. Community vote required for any permanent migration, but temporary operational measures can be taken under council authority.

**Regulatory events.** Legal or regulatory events requiring immediate action (receipt of court order, jurisdictional prohibition, etc.). Council can take necessary protective actions with retrospective community vote.

Emergency actions are always disclosed publicly and subject to community review. Council members can be recalled via governance vote if they misuse emergency powers.

---

## Transparency

Governance operates in public:

**Proposal archive.** All submitted proposals, discussions, votes, and outcomes are publicly archived.

**Vote records.** Individual votes by major delegates and council members are public. Pseudonymous voting by smaller rFOAF holders is preserved for privacy.

**Treasury visibility.** All foundation and DAO treasury addresses are public. Movements can be independently verified on-chain.

**Participation dashboards.** Real-time metrics on governance participation, delegate performance, voter turnout, and proposal volume.

**Periodic governance reports.** Quarterly reports summarize governance activity, key decisions, treasury movements, and participation trends.

---

## Evolution of Governance

Governance mechanics will evolve as the protocol matures. Expected evolution:

### Phase 1 (current): Foundation-controlled

- No DAO yet.
- Foundation team makes all decisions.
- Community input via forum and informal channels.
- This document describes the intended end state; Phase 1 operates under foundation authority.

### Phase 2: Pilot governance

- rFOAF smart contracts deployed but with limited scope.
- First DAO votes on low-stakes matters (e.g., forum moderation, community grants).
- Foundation retains authority over protocol and treasury but tests governance mechanics.

### Phase 3: DAO activation

- rFOAF fully operational.
- Protocol parameters come under DAO governance.
- Treasury partially transitions to DAO control.
- Foundation retains emergency powers but most decisions go through DAO.

### Phase 4+: Full DAO governance

- Treasury fully under DAO control.
- Foundation minority role only; founder members hold rFOAF like other participants.
- Emergency council elected by DAO.
- This document's final form.

See [DAO Transition](./dao-transition.md) for detailed timeline.

---

## Relationship to Other Documents

- [Tokenomics](./tokenomics.md) — defines FOAF and RHEO; rFOAF is defined here.
- [Fee Structure](./fee-structure.md) — defines what fees exist; governance determines rates.
- [Treasury and Operations](./treasury-and-operations.md) — treasury management operates under governance after transition.
- [Team Vesting](./team-vesting.md) — team FOAF becomes governance-participating once vested and locked into rFOAF.
- [DAO Transition](./dao-transition.md) — timeline for activating governance mechanisms described here.
- [Node Operators](../technical/node-operators.md) — node operator role interacts with rFOAF via staking requirements.
