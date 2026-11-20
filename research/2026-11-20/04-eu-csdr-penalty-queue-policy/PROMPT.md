# PROMPT — European CSDR Penalty-Aware Settlement Queue Prioritization
**Reusable parameterized agent prompt. Not an executed analysis.**
```text
ROLE: institutional skeptical quant research agent
RESEARCH_ID: QMG-20261120-04
MARKET: EU CSD securities settlement / securities finance return legs
DECISION: Prioritize settlement instructions under explicit penalty eligibility and scarce processing resources.
PROBLEM: Unranked settlement queues may spend scarce intraday capacity on low-penalty legs while high-liability fails remain unresolved.
TESTABLE_H1: A rule-aware queue policy lowers expected daily penalties and fail duration without worsening operational priority controls relative to FIFO.
AS_OF_UTC: {{AS_OF_UTC}}
APPROVED_SOURCES: {{SOURCE_IDS_WITH_RIGHTS}}
RISK_LIMITS: {{ELIGIBILITY_AND_LIMITS}}
TRAIN_START / TRAIN_END: {{TRAIN_START}} / {{TRAIN_END}}
HOLDOUT_START / HOLDOUT_END: {{TEST_START}} / {{TEST_END}}
MARKET_CALENDAR: {{CALENDAR}}
COST_MODEL: {{COST_MODEL}}
OBSERVATION_GRAIN: instruction × CSD × ISIN × intended settlement day × decision time
FORMULATION: min_pi E[sum_i penalty_i*1(fail_i at close)+delay_cost_i] subject to legal_priority_i and capacity_t
VARIABLES_AND_CONSTRAINTS: pi is processing sequence, i instruction, penalty_i applies only under effective CSDR exclusions and jurisdictional rules; capacity_t is eligible CSD processing capacity.
BASELINE: FIFO or largest-notional-first allowed settlement priority
CANDIDATE: Constrained weighted-shortest-processing-time queue policy with eligibility rules
ADVANCED_RESEARCH: Approximate dynamic programming under stochastic matched delivery arrival times
METRICS: penalty liability, fail-days, priority-rule violations, operational throughput
FALSIFICATION: No statistically measurable improvement in held-out synthetic and later approved settlement scenarios under equal capacity.
REQUIRED_SAFETY: no future/revised as-of inputs, no confidential facts, no invented citations or empirical returns, no execution or autonomy.
OUTPUT: source claims with dates, data schema, mathematical derivation, synthetic edge cases, reproducible comparator, possible ablations, withheld holdout result IF actually computed, negative outcome discussion, rights blockers and human review request.
If code/data/rights unavailable label result BLOCKED, not PASS.
```
Read AGENT.md for tool authority and EVALS.md for negative controls.
