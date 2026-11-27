# EVALS — European Interconnector Congestion Power-Spread State Estimator
**No empirical test run. Evaluation design, not evidence.**

## H1/H0 and economics
H1: Transmission-capacity-corrected congestion states improve next-day risk classification and hedge calibration versus load-only spread models.
H0: the feasible `Historical seasonal hourly spread by zone pair` benchmark is not improved net of risk/cost.
Candidate: `Physical-congestion regime HMM with capacity-constrained exposure mapper`. Advanced: Stochastic DC power flow and multi-region graph forecasts with out-of-area transfer shadow prices
Metrics: Congestion regime Brier score, spread MAE, feasible net hedge carry and stress CVaR.

## Mandatory synthetic invariants
- `available_at_utc <= decision_time`, calendar/session alignment and source-version hash.
- Feasible decision constraints match: Spread_{a,b,t}=Price_a,t-Price_b,t; Flow_{ab,t}≤ATC_{ab,t}; max_q E[q*Spread-CongestionCost(q)] with |q|≤AccessCap.
- Units and payable/receivable cash direction from: a,b bidding zones; ATC available transfer capacity; q a hypothetical permitted hedge, not a physically available arbitrage.
- True negative controls: Cross-zone transmission rights and operational capacities not freely tradable; timestamps and price revisions.
- Equal event/asset universe, quoted bid/ask, capacity and no-action alternatives.

## Empirical design if licensed data eventually approved
Time-blocked train/validation/holdout, embargo overlaps and original-vintage release lags. Conduct matched policy replay, bootstrap by independent event block, monitor false discoveries across multiple choices, expose failed dates and liquidity drawdowns.
**Stop:** Spread gains disappear after simultaneous public forecast access, congestion settlement and capacity rights..

## Cost and publication
Transmission rights/market access and collateral requirements dominate quoted spread opportunities.
$220k assumed total 24m development/data/maintenance cost; assumed launch in month 9; assumed annual gross outcome downside/base/upside $0k/$150k/$355k. Resulting 24m net ROI **-100.0% / -14.8% / 101.7% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
Public papers and official datasets are context only, not replication. Any material positive result requires independently reproduced code + signed human review; no automatic trading.

## Acceptance gating
AC-001..AC-005 from SPEC each requires a runnable test record and model/data rights signoff. If source is incomplete, report a negative or blocked result, not a proxy alpha claim.
