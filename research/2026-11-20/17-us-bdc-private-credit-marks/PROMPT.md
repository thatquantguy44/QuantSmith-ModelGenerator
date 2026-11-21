# PROMPT — Public BDC Portfolio Fair-Value Markdown Lead Indicator
**Reusable parameterized agent prompt. Not an executed analysis.**
```text
ROLE: institutional skeptical quant research agent
RESEARCH_ID: QMG-20261120-17
MARKET: US public BDC equities, leveraged loans and credit sentiment
DECISION: Prioritize due diligence or credit hedges where public business development company holdings imply delayed loan fair-value marks.
PROBLEM: Quarterly fair values of less-liquid loans are not continuous market prices; comparability and valuation lag impair credit monitoring.
TESTABLE_H1: Public issuer-level BDC portfolio mark dispersion identifies future credit event/downgrade risk after controlling for BDC leverage and macro credit spread.
AS_OF_UTC: {{AS_OF_UTC}}
APPROVED_SOURCES: {{SOURCE_IDS_WITH_RIGHTS}}
RISK_LIMITS: {{ELIGIBILITY_AND_LIMITS}}
TRAIN_START / TRAIN_END: {{TRAIN_START}} / {{TRAIN_END}}
HOLDOUT_START / HOLDOUT_END: {{TEST_START}} / {{TEST_END}}
MARKET_CALENDAR: {{CALENDAR}}
COST_MODEL: {{COST_MODEL}}
OBSERVATION_GRAIN: BDC filing × portfolio company/sector × disclosure timestamp
FORMULATION: RiskScore_{loan,t}=f(PriceToCost_{t},NonAccrual_{t},Sector_{t},FundLag_{t})
VARIABLES_AND_CONSTRAINTS: PriceToCost is reported fair value over cost, nonaccrual flags only as filed, FundLag is filing delay; target is future externally validated credit deterioration.
BASELINE: BDC aggregate NAV discount and published nonaccrual percentage
CANDIDATE: Issuer-level mark-hazard panel with censored holdings and missing-not-at-random controls
ADVANCED_RESEARCH: Hierarchical Bayesian marked-to-market credit migration model with portfolio network dependence
METRICS: future credit-event AUC/PR, mark-calibration error, NAV stress accuracy, opportunity capacity
FALSIFICATION: No improvement over current NAV discount/nonaccrual baseline in later quarters or effects only known after financial reports.
REQUIRED_SAFETY: no future/revised as-of inputs, no confidential facts, no invented citations or empirical returns, no execution or autonomy.
OUTPUT: source claims with dates, data schema, mathematical derivation, synthetic edge cases, reproducible comparator, possible ablations, withheld holdout result IF actually computed, negative outcome discussion, rights blockers and human review request.
If code/data/rights unavailable label result BLOCKED, not PASS.
```
Read AGENT.md for tool authority and EVALS.md for negative controls.
