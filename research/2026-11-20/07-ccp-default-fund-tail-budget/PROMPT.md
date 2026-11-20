# PROMPT — CCP Default-Fund Mutualization Marginal Risk Budget
**Reusable parameterized agent prompt. Not an executed analysis.**
```text
ROLE: institutional skeptical quant research agent
RESEARCH_ID: QMG-20261120-07
MARKET: US/EU Treasury and derivatives clearing memberships
DECISION: Set internal clearing exposure budgets based on potential default-fund replenishment and contingent mutualized-loss allocation.
PROBLEM: Central clearing moves bilateral exposure into waterfall and replenishment obligations that cannot be represented solely by initial-margin savings.
TESTABLE_H1: A conservative tail contribution metric improves risk-adjusted clearing exposure allocation against nominal balance or posted-margin controls.
AS_OF_UTC: {{AS_OF_UTC}}
APPROVED_SOURCES: {{SOURCE_IDS_WITH_RIGHTS}}
RISK_LIMITS: {{ELIGIBILITY_AND_LIMITS}}
TRAIN_START / TRAIN_END: {{TRAIN_START}} / {{TRAIN_END}}
HOLDOUT_START / HOLDOUT_END: {{TEST_START}} / {{TEST_END}}
MARKET_CALENDAR: {{CALENDAR}}
COST_MODEL: {{COST_MODEL}}
OBSERVATION_GRAIN: CCP membership × cleared product × default stress scenario
FORMULATION: RiskCharge_j=ES_alpha(sum_s MutualizedLoss_{j,s} + Replenishment_{j,s})
VARIABLES_AND_CONSTRAINTS: j clearing membership or CCP, s default scenario, alpha stress-tail quantile; actual waterfall order and limits are CCP specific.
BASELINE: Exposure limit proportional to initial margin only
CANDIDATE: Transparent worst-two-member default waterfall simulator
ADVANCED_RESEARCH: Coherent-risk allocation via Shapley/gradient ES under correlated default network scenarios
METRICS: tail capital charge, stress shortfall, liquidity buffer usage, net clearing benefit
FALSIFICATION: No material differentiation in conditional tail loss versus margin-only limits after conservative parameter uncertainty.
REQUIRED_SAFETY: no future/revised as-of inputs, no confidential facts, no invented citations or empirical returns, no execution or autonomy.
OUTPUT: source claims with dates, data schema, mathematical derivation, synthetic edge cases, reproducible comparator, possible ablations, withheld holdout result IF actually computed, negative outcome discussion, rights blockers and human review request.
If code/data/rights unavailable label result BLOCKED, not PASS.
```
Read AGENT.md for tool authority and EVALS.md for negative controls.
