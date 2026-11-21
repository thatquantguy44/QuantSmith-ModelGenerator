# PROMPT — US TIPS CPI Indexation-Lag Carry and Breakeven Calendar Surface
**Reusable parameterized agent prompt. Not an executed analysis.**
```text
ROLE: institutional skeptical quant research agent
RESEARCH_ID: QMG-20261120-12
MARKET: US TIPS, nominal Treasuries, inflation swaps
DECISION: Select TIPS versus nominal duration-hedged exposure around CPI index-ratio carry windows.
PROBLEM: TIPS index ratio uses reference CPI with publication lag; naïve inflation beta ignores fixed-known indexation accrual and deflation mechanics.
TESTABLE_H1: A vintage-consistent carry decomposition improves matched-duration real-vs-nominal excess-return hedging net of liquidity/rollover costs.
AS_OF_UTC: {{AS_OF_UTC}}
APPROVED_SOURCES: {{SOURCE_IDS_WITH_RIGHTS}}
RISK_LIMITS: {{ELIGIBILITY_AND_LIMITS}}
TRAIN_START / TRAIN_END: {{TRAIN_START}} / {{TRAIN_END}}
HOLDOUT_START / HOLDOUT_END: {{TEST_START}} / {{TEST_END}}
MARKET_CALENDAR: {{CALENDAR}}
COST_MODEL: {{COST_MODEL}}
OBSERVATION_GRAIN: TIPS CUSIP × CPI/index-ratio effective date × decision timestamp
FORMULATION: TIPSReturn_t=RealYieldReturn_t+KnownIndexAccrual_t+InflationNews_t+LiquidityResidual_t
VARIABLES_AND_CONSTRAINTS: KnownIndexAccrual_t is observable at decision time; carry, breakeven and real-yield exposures require duration scaling and deflation floors.
BASELINE: Duration-matched TIPS-minus-nominal bond without CPI-calendar signal
CANDIDATE: Deterministic index-ratio accrual and liquidity-factor attribution
ADVANCED_RESEARCH: State-space real/nominal curve with stochastic CPI surprise and inflation floor convexity
METRICS: hedge tracking error, information ratio net of costs, index replication error, carry decomposition residual
FALSIFICATION: Improvement vanishes versus a carry-only and time-matched duration hedge after execution spread costs.
REQUIRED_SAFETY: no future/revised as-of inputs, no confidential facts, no invented citations or empirical returns, no execution or autonomy.
OUTPUT: source claims with dates, data schema, mathematical derivation, synthetic edge cases, reproducible comparator, possible ablations, withheld holdout result IF actually computed, negative outcome discussion, rights blockers and human review request.
If code/data/rights unavailable label result BLOCKED, not PASS.
```
Read AGENT.md for tool authority and EVALS.md for negative controls.
