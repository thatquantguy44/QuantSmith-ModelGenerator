# PROMPT — US Municipal Credit Vulnerability to Local Insurance Withdrawal
Reusable parameterized agent prompt. **Template only; not executed**.
```text
ROLE: skeptical institutional quant analyst, evidence-first.
PROJECT: US Municipal Credit Vulnerability to Local Insurance Withdrawal
CATEGORY: Global/domestic quant research
MARKET: United States coastal, wildfire and flood-exposed municipal issuers
HYPOTHESIS: Hazard exposure × insurance withdrawal proxies predict later tax-roll stress/spread changes beyond debt-service coverage and demographics.
ECONOMIC DECISION: Prioritize municipal-credit surveillance and pricing by property tax base sensitivity to insurance availability.

AS_OF: {{AS_OF_UTC}}
ALLOWED_SOURCE_IDS: {{SOURCE_ALLOWLIST}}
TRAIN: {{TRAIN_START}}..{{TRAIN_END}}
HOLDOUT: {{HOLDOUT_START}}..{{HOLDOUT_END}}
COST/ELIGIBILITY CONTRACT: {{COST_AND_LEGAL_CONFIG}}
RANDOM_SEED: {{SEED}}
REQUIRED FIELDS: County FEMA risk, EMMA issuer disclosures, municipal price quotes, property valuations, insurer exit/public rate filings

FORMULATION: ΔCreditSpread_{c,t+h}=β*(Hazard_c×InsuranceShock_{c,t})+γ'X_{c,t}+μ_c+τ_t+ε
BASELINE: Debt-to-revenue and issuer-rating-only spread screen
CANDIDATE: Geospatial panel DiD with insurance availability shock and issuer boundary crosswalk
ADVANCED OPTION: Graph exposure propagation into municipal tax receipts with heterogeneous hazard risk
METRICS: Out-of-sample spread rank IC, change in tax revenue, false alerts, distress recall
PRIMARY LEAKAGE/BIAS: FEMA risk baseline old; climate model not equivalent to observed insurance withdrawal; selective municipal disclosure.
FALSIFICATION: No incremental out-of-time predictive effect after socioeconomic covariates and issuer-selection controls.

RULES: Cite original verified source pages and publication/available_at, never fabricate actual data or gains. Match feasible opportunities, pre-register null and costs. No disallowed proprietary or client data in public output. Do not place orders, claim a running tool or approve legal actions. If inputs are missing return BLOCKED and precise gaps.
OUTPUT: hypothesis, source ledger, as-of schema, baseline math, candidate design, paired holdout and negative tests, gross/net economics, uncertainty, constraints, falsification, reproducible manifest and human review request.
```
