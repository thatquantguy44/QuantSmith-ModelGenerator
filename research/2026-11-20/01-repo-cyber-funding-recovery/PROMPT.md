# PROMPT — Cyber-Outage Contingent Repo Funding Recovery Routes
**Reusable parameterized agent prompt. Not an executed analysis.**
```text
ROLE: institutional skeptical quant research agent
RESEARCH_ID: QMG-20261120-01
MARKET: US cleared and tri-party repo
DECISION: Pre-approve alternate cash-lender/clearing routes and reserve a minimum contingency liquidity buffer for an exogenous operational outage.
PROBLEM: A temporary lender or settlement-node cyber outage can strand otherwise sound secured funding even with sufficient collateral.
TESTABLE_H1: Conditional multi-route recovery decreases funding shortfall and expected disruption cost more than an equal-cost static backup buffer.
AS_OF_UTC: {{AS_OF_UTC}}
APPROVED_SOURCES: {{SOURCE_IDS_WITH_RIGHTS}}
RISK_LIMITS: {{ELIGIBILITY_AND_LIMITS}}
TRAIN_START / TRAIN_END: {{TRAIN_START}} / {{TRAIN_END}}
HOLDOUT_START / HOLDOUT_END: {{TEST_START}} / {{TEST_END}}
MARKET_CALENDAR: {{CALENDAR}}
COST_MODEL: {{COST_MODEL}}
OBSERVATION_GRAIN: route × lender class × hourly outage scenario
FORMULATION: min_{x,b} E_s[ FundingGap_s(x,b)*p_s + SwitchingCost_s(x) ] + CarryCost(b)
VARIABLES_AND_CONSTRAINTS: x are route and lender allocation decisions, b is reserved liquidity, p_s is the unit shortfall penalty in outage scenario s; legal availability, committed limits and collateral eligibility bound x.
BASELINE: Fixed 10% contingency funding buffer with one permitted fallback
CANDIDATE: Two-stage robust multi-commodity flow with cyber failure scenarios
ADVANCED_RESEARCH: Distributionally robust scenario-tree route control with simultaneous correlated cash-lender disruptions
METRICS: shortfall dollars, p95 duration, liquidity carry, fail probability, recovery cost
FALSIFICATION: Held-out synthetic/approved outage replay fails to reduce mean + tail shortfall at fixed total contingency cost.
REQUIRED_SAFETY: no future/revised as-of inputs, no confidential facts, no invented citations or empirical returns, no execution or autonomy.
OUTPUT: source claims with dates, data schema, mathematical derivation, synthetic edge cases, reproducible comparator, possible ablations, withheld holdout result IF actually computed, negative outcome discussion, rights blockers and human review request.
If code/data/rights unavailable label result BLOCKED, not PASS.
```
Read AGENT.md for tool authority and EVALS.md for negative controls.
