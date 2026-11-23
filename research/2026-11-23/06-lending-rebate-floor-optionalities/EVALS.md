# EVALS — Securities Lending Cash Rebate Floor Optionality in Low-Rate Regimes
**No empirical test run. Evaluation design, not evidence.**

## H1/H0 and economics
H1: Contract-aware nonlinear floor valuation reduces forecast carry error and improper pricing vs linear spread assumptions.
H0: the feasible `Static contractual rebate minus benchmark with no optionality` benchmark is not improved net of risk/cost.
Candidate: `Rate-tree floor valuation and curve calibration with contract clause parser`. Advanced: Multi-currency short-rate stochastic volatility and correlated collateral run-off scenario valuation
Metrics: Pricing replication error, stress carry, calibration error and limit-breach count.

## Mandatory synthetic invariants
- `available_at_utc <= decision_time`, calendar/session alignment and source-version hash.
- Feasible decision constraints match: PV_floor=E^Q[Σ_t DF_t*CashCollateral_t*max(K-r_t,0)*Δt]; Revenue=baseFee+PV_floor-hedgeCost.
- Units and payable/receivable cash direction from: K is contractual rebate floor, r_t relevant overnight collateral rate, DF discount factor, Δt year fraction.
- True negative controls: Floor rights and term structures vary by legal agreement; historic negative-rate regimes have sample limitations.
- Equal event/asset universe, quoted bid/ask, capacity and no-action alternatives.

## Empirical design if licensed data eventually approved
Time-blocked train/validation/holdout, embargo overlaps and original-vintage release lags. Conduct matched policy replay, bootstrap by independent event block, monitor false discoveries across multiple choices, expose failed dates and liquidity drawdowns.
**Stop:** Valuation adds no meaningful incremental pricing accuracy to conservative quoted-fee schedules..

## Cost and publication
Profit only if floors contractually negotiated; hedge notional and floor illiquidity restrict scale.
$135k assumed total 24m development/data/maintenance cost; assumed launch in month 7; assumed annual gross outcome downside/base/upside $0k/$80k/$225k. Resulting 24m net ROI **-100.0% / -16.0% / 136.1% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
Public papers and official datasets are context only, not replication. Any material positive result requires independently reproduced code + signed human review; no automatic trading.

## Acceptance gating
AC-001..AC-005 from SPEC each requires a runnable test record and model/data rights signoff. If source is incomplete, report a negative or blocked result, not a proxy alpha claim.
