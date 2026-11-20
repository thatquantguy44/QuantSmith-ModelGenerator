# PROMPT — Wheat Export Inspection Revisions to Global Basis and Calendar Spreads
**Reusable parameterized agent prompt. Not an executed analysis.**
```text
ROLE: institutional skeptical quant research agent
RESEARCH_ID: QMG-20261120-18
MARKET: US, Black Sea and international wheat futures/physical flows
DECISION: Hedge wheat calendar spreads around official export inspection versus world balance-sheet information releases.
PROBLEM: Weekly port inspection momentum and monthly USDA supply tables arrive at different times and may contain meaningful revisions.
TESTABLE_H1: Vintage-corrected inspection surprises anticipate regional wheat basis and nearby-deferred spread movements beyond seasonality and WASDE.
AS_OF_UTC: {{AS_OF_UTC}}
APPROVED_SOURCES: {{SOURCE_IDS_WITH_RIGHTS}}
RISK_LIMITS: {{ELIGIBILITY_AND_LIMITS}}
TRAIN_START / TRAIN_END: {{TRAIN_START}} / {{TRAIN_END}}
HOLDOUT_START / HOLDOUT_END: {{TEST_START}} / {{TEST_END}}
MARKET_CALENDAR: {{CALENDAR}}
COST_MODEL: {{COST_MODEL}}
OBSERVATION_GRAIN: weekly USDA inspection release × grain class × destination × exchange quote timestamp
FORMULATION: BasisChange_{r,t+h}=alpha+beta*(InspectionsPublished_t-ExpectedInspections_t)+gamma*Weather_t+epsilon
VARIABLES_AND_CONSTRAINTS: r region; expected inspections estimated using only pre-release history; h is post-release decision horizon with realistic market access.
BASELINE: Monthly seasonal wheat spread regression using last known WASDE
CANDIDATE: Mixed-frequency distributed-lag export surprise model
ADVANCED_RESEARCH: Structural Bayesian crop-flow network with regional stock constraints and censoring
METRICS: spread forecast delta, regional basis tracking, net slippage-adjusted hedge P&L, regime robustness
FALSIFICATION: No predictive improvement after weather, futures calendar effects and contemporaneous official release lags.
REQUIRED_SAFETY: no future/revised as-of inputs, no confidential facts, no invented citations or empirical returns, no execution or autonomy.
OUTPUT: source claims with dates, data schema, mathematical derivation, synthetic edge cases, reproducible comparator, possible ablations, withheld holdout result IF actually computed, negative outcome discussion, rights blockers and human review request.
If code/data/rights unavailable label result BLOCKED, not PASS.
```
Read AGENT.md for tool authority and EVALS.md for negative controls.
