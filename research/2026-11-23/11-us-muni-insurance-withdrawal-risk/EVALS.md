# EVALS — US Municipal Credit Vulnerability to Local Insurance Withdrawal
**No empirical test run. Evaluation design, not evidence.**

## H1/H0 and economics
H1: Hazard exposure × insurance withdrawal proxies predict later tax-roll stress/spread changes beyond debt-service coverage and demographics.
H0: the feasible `Debt-to-revenue and issuer-rating-only spread screen` benchmark is not improved net of risk/cost.
Candidate: `Geospatial panel DiD with insurance availability shock and issuer boundary crosswalk`. Advanced: Graph exposure propagation into municipal tax receipts with heterogeneous hazard risk
Metrics: Out-of-sample spread rank IC, change in tax revenue, false alerts, distress recall.

## Mandatory synthetic invariants
- `available_at_utc <= decision_time`, calendar/session alignment and source-version hash.
- Feasible decision constraints match: ΔCreditSpread_{c,t+h}=β*(Hazard_c×InsuranceShock_{c,t})+γ'X_{c,t}+μ_c+τ_t+ε.
- Units and payable/receivable cash direction from: c is issuer county/service area, h forward horizon; InsuranceShock uses published insurer exit/premium information.
- True negative controls: FEMA risk baseline old; climate model not equivalent to observed insurance withdrawal; selective municipal disclosure.
- Equal event/asset universe, quoted bid/ask, capacity and no-action alternatives.

## Empirical design if licensed data eventually approved
Time-blocked train/validation/holdout, embargo overlaps and original-vintage release lags. Conduct matched policy replay, bootstrap by independent event block, monitor false discoveries across multiple choices, expose failed dates and liquidity drawdowns.
**Stop:** No incremental out-of-time predictive effect after socioeconomic covariates and issuer-selection controls..

## Cost and publication
Muni bonds illiquid, spread carry/horizon may exceed signal; favor risk-monitoring before trading.
$160k assumed total 24m development/data/maintenance cost; assumed launch in month 7; assumed annual gross outcome downside/base/upside $0k/$100k/$260k. Resulting 24m net ROI **-100.0% / -11.5% / 130.2% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
Public papers and official datasets are context only, not replication. Any material positive result requires independently reproduced code + signed human review; no automatic trading.

## Acceptance gating
AC-001..AC-005 from SPEC each requires a runnable test record and model/data rights signoff. If source is incomplete, report a negative or blocked result, not a proxy alpha claim.
