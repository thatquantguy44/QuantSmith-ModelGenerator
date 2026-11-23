# EVALS — OPEC Oil Balance Residuals and Refined Crack-Spread Transmission
**No empirical test run. Evaluation design, not evidence.**

## H1/H0 and economics
H1: JODI stock-flow residuals after publication improve future refined crack-spread risk forecasts over oil price and seasonal inventories.
H0: the feasible `Seasonal EIA weekly inventories and oil curve` benchmark is not improved net of risk/cost.
Candidate: `Constrained oil balance reconciliation and local-projection crack spread model`. Advanced: Multi-region Bayesian trade flow accounting with measurement error and shipping lags
Metrics: Out-of-sample crack variance forecast, economic hedge cost, stock-balance residual stability.

## Mandatory synthetic invariants
- `available_at_utc <= decision_time`, calendar/session alignment and source-version hash.
- Feasible decision constraints match: Residual_{c,m}=Production+Imports-Exports-RefineryIntake-ΔStocks-OtherUse; Crack_t=P_product_t-ConversionRatio*P_crude_t.
- Units and payable/receivable cash direction from: c country,m reporting month; residual is diagnostic with units normalized; price conversion reflects barrel yields.
- True negative controls: Monthly country submission corrections, unit conversion mismatches and sanctioned flow missingness.
- Equal event/asset universe, quoted bid/ask, capacity and no-action alternatives.

## Empirical design if licensed data eventually approved
Time-blocked train/validation/holdout, embargo overlaps and original-vintage release lags. Conduct matched policy replay, bootstrap by independent event block, monitor false discoveries across multiple choices, expose failed dates and liquidity drawdowns.
**Stop:** Residual predictive content disappears after vintages, shipping lags and front-month liquidity adjustment..

## Cost and publication
Use executable refined product futures, contract rolls, inventory and liquidity spreads; no inference from paper spreads.
$170k assumed total 24m development/data/maintenance cost; assumed launch in month 7; assumed annual gross outcome downside/base/upside $0k/$115k/$280k. Resulting 24m net ROI **-100.0% / -4.2% / 133.3% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
Public papers and official datasets are context only, not replication. Any material positive result requires independently reproduced code + signed human review; no automatic trading.

## Acceptance gating
AC-001..AC-005 from SPEC each requires a runnable test record and model/data rights signoff. If source is incomplete, report a negative or blocked result, not a proxy alpha claim.
