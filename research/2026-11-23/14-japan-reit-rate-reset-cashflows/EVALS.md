# EVALS — Japanese Real-Estate Equity Cash-Flow Sensitivity to BOJ Rate Normalization
**No empirical test run. Evaluation design, not evidence.**

## H1/H0 and economics
H1: Public debt-maturity reset exposure explains post-policy J-REIT return dispersion beyond NAV discount and generic duration beta.
H0: the feasible `Market REIT index duration and price-to-NAV score` benchmark is not improved net of risk/cost.
Candidate: `Disclosure-derived maturity-wall factor with event-based hedged return regressions`. Advanced: Tenant lease rollover and financing reset structural cash-flow model
Metrics: AFFO forecast error, sector-neutral return IC, liquidity-adjusted drawdown, event placebo.

## Mandatory synthetic invariants
- `available_at_utc <= decision_time`, calendar/session alignment and source-version hash.
- Feasible decision constraints match: CashInterest_{i,t+h}=Σ_m Debt_{i,m}*(Coupon_{i,m}+ResetBeta_{i,m}*ΔRate_t); ΔAFFO_i≈-ΔCashInterest_i+RentPassThrough_i.
- Units and payable/receivable cash direction from: i REIT, m debt tranche, ResetBeta contractual floating/reset sensitivity; AFFO cash flow.
- True negative controls: Japanese disclosure translation/lease renewal timing and selective REIT survivorship.
- Equal event/asset universe, quoted bid/ask, capacity and no-action alternatives.

## Empirical design if licensed data eventually approved
Time-blocked train/validation/holdout, embargo overlaps and original-vintage release lags. Conduct matched policy replay, bootstrap by independent event block, monitor false discoveries across multiple choices, expose failed dates and liquidity drawdowns.
**Stop:** No incremental post-rate-shift forecast after issuer fixed-effects and NAV-duration controls..

## Cost and publication
J-REIT constituent liquidity, FX hedge and foreign-investor restrictions limit realized capacity.
$150k assumed total 24m development/data/maintenance cost; assumed launch in month 7; assumed annual gross outcome downside/base/upside $0k/$85k/$235k. Resulting 24m net ROI **-100.0% / -19.7% / 121.9% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
Public papers and official datasets are context only, not replication. Any material positive result requires independently reproduced code + signed human review; no automatic trading.

## Acceptance gating
AC-001..AC-005 from SPEC each requires a runnable test record and model/data rights signoff. If source is incomplete, report a negative or blocked result, not a proxy alpha claim.
