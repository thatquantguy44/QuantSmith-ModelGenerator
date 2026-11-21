# European CSDR Penalty-Aware Settlement Queue Prioritization
**Project ID:** QMG-20261120-04 · **Category:** SECURITIES FINANCE · **Score:** 92/100 (editorial) · **State:** proposal, no code/tests/empirical results.

## Market and decision
EU CSD securities settlement / securities finance return legs. Unranked settlement queues may spend scarce intraday capacity on low-penalty legs while high-liability fails remain unresolved.

**Decision:** Prioritize settlement instructions under explicit penalty eligibility and scarce processing resources.

## Explicit falsifiable research question
A rule-aware queue policy lowers expected daily penalties and fail duration without worsening operational priority controls relative to FIFO.

## Mathematical objective (research formulation, not calibrated)
```text
min_pi E[sum_i penalty_i*1(fail_i at close)+delay_cost_i] subject to legal_priority_i and capacity_t
```
**Variables and hard constraints:** pi is processing sequence, i instruction, penalty_i applies only under effective CSDR exclusions and jurisdictional rules; capacity_t is eligible CSD processing capacity.

## Data and timing
**Required:** Public ESMA CSDR framework, synthetic ISIN liquidity/penalty groups, settlement instruction cutoff, fail reason and amendment history. **Observation grain:** instruction × CSD × ISIN × intended settlement day × decision time. **As-of rule:** Penalty exclusions and rules must reflect versions legally in force before each instruction decision; ESMA technical advice is not automatically operative law.

## Design options
- **Feasible baseline:** FIFO or largest-notional-first allowed settlement priority.
- **Candidate research method:** Constrained weighted-shortest-processing-time queue policy with eligibility rules.
- **Advanced counterfactual:** Approximate dynamic programming under stochastic matched delivery arrival times.
- **Metrics:** penalty liability, fail-days, priority-rule violations, operational throughput.
- **Falsification / no-go:** No statistically measurable improvement in held-out synthetic and later approved settlement scenarios under equal capacity.
- **Primary leakage and identification risk:** Misclassification of non-attributable fail causes or legal exclusion yields incorrect optimized queues..

## Economic and production screening
Settlement bandwidth/available inventory and mandatory processing priority; adverse-penalty reallocations cannot violate service commitments.

**Difficulty:** Medium-high; **production feasibility:** High as rule-replay prototype; **publication value:** Legal-constraint-aware stochastic queue scheduling.
**24-month ROI sensitivity:** $145k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 7 months; annual gross benefit scenarios $0k / $100k / $250k (downside/base/upside) for the remaining 1.4166666666666667 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -2.3% / 144.3%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Evidence and novelty
Differs from past buy-in-vs-wait timing and settlement contagion: this chooses *ex-ante* multi-instruction processing order under cash penalty rules.
- **ESMA CSDR Article 7 settlement-fail measures** (regulation, current rulebook checked 2026-11-20): [official source](https://www.esma.europa.eu/publications-and-data/interactive-single-rulebook/csdr/article-7-measures-address-settlement-0). Daily cash penalties with exclusions; jurisdictional and effective-date reviews required.
- **ESMA cash penalty scope technical advice** (regulatory technical advice, 2025-06-26): [official source](https://www.esma.europa.eu/node/219934). Advice is not automatically operative law; capture adopted delegated acts separately.

## Navigation
[Spec](SPEC.md) · [Plan](PLAN.md) · [Tasks](TASKS.md) · [Roadmap](ROADMAP.md) · [Handoff](HANDOFF.md) · [Sources](SOURCES.md) · [Agent](AGENT.md) · [Skill](SKILL.md) · [Prompt](PROMPT.md) · [Tooling](TOOLING.md) · [Workflow](WORKFLOW.md) · [Runtime](RUNTIME.md) · [Evals](EVALS.md)

**Research design only.** Market data, human approval, trading capabilities and deployable software do not yet exist in this folder.
