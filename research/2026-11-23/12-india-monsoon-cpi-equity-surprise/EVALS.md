# EVALS — India Monsoon Surprise to Food CPI and Local Equity Pricing
**No empirical test run. Evaluation design, not evidence.**

## H1/H0 and economics
H1: Rainfall surprises weighted by district crop patterns predict food-CPI subcomponents and cross-sectional consumer equity earnings revisions beyond national rainfall.
H0: the feasible `All-India seasonal rainfall deviation plus autoregressive food CPI` benchmark is not improved net of risk/cost.
Candidate: `Hierarchical spatial distributed-lag regression + causal crop weighting`. Advanced: Weather-to-crop graph structural state-space model with uncertainty propagation
Metrics: CPI MAE, sector neutral-return IC, hit rate net costs, seasonal robustness.

## Mandatory synthetic invariants
- `available_at_utc <= decision_time`, calendar/session alignment and source-version hash.
- Feasible decision constraints match: Shock_t=Σ_d CropWeight_d*(Rain_d,t - Normal_d,t); ΔCPI_{t+h}=α+β*Shock_t+γ'Controls_t+ε.
- Units and payable/receivable cash direction from: d district; crop weights fixed pre-season; h forecast horizon; normals from training vintage.
- True negative controls: Historical IMD OGD resources lag, crop mix revisions, rainfall not yield and policy interventions.
- Equal event/asset universe, quoted bid/ask, capacity and no-action alternatives.

## Empirical design if licensed data eventually approved
Time-blocked train/validation/holdout, embargo overlaps and original-vintage release lags. Conduct matched policy replay, bootstrap by independent event block, monitor false discoveries across multiple choices, expose failed dates and liquidity drawdowns.
**Stop:** No incremental holdout inflation forecast or stock-return effect against rainfall benchmark..

## Cost and publication
Large liquid Indian stocks capacity feasible only with correct foreign-investor access, FX costs and exchange calendars.
$160k assumed total 24m development/data/maintenance cost; assumed launch in month 7; assumed annual gross outcome downside/base/upside $0k/$100k/$240k. Resulting 24m net ROI **-100.0% / -11.5% / 112.5% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
Public papers and official datasets are context only, not replication. Any material positive result requires independently reproduced code + signed human review; no automatic trading.

## Acceptance gating
AC-001..AC-005 from SPEC each requires a runnable test record and model/data rights signoff. If source is incomplete, report a negative or blocked result, not a proxy alpha claim.
