# EVALS — Agency MBS Dollar-Roll Cheapest-to-Deliver Financing Option
**No empirical test run. Evaluation design, not evidence.**

## H1/H0 and economics
H1: Explicit deliverability and pool opportunity costs explain dollar-roll implied funding differences beyond coupon, term and simple financing spreads.
H0: the feasible `Dollar-roll implied financing vs same-tenor generic repo without delivery-option valuation` benchmark is not improved net of risk/cost.
Candidate: `Constrained pool-delivery optimizer with observable pool financing carry and roll prices`. Advanced: Stochastic pool quality and delivery-selection real-options game with cheapest-deliverable simulation
Metrics: Net financing bps, cheapest-deliverable premium, pre-settlement fail exposure, netted capital and tail regret.

## Mandatory synthetic invariants
- `available_at_utc <= decision_time`, calendar/session alignment and source-version hash.
- Feasible decision constraints match: min_{x_p in {0,1}} Σ_p x_p*(PoolCarry_p + DeliveryCost_p - RollDrop_p), subject to Σ_p x_p = DeliverableNotional, Eligible_p=1.
- Units and payable/receivable cash direction from: x_p is assigned pool fraction/selection, RollDrop is dollar-roll price drop, Eligible_p delivery eligibility; preserve coupon/payup units.
- True negative controls: Pool price selection, payup optionality, actual pool availability and post-trade EPN leakage.
- Equal event/asset universe, quoted bid/ask, capacity and no-action alternatives.

## Empirical design if licensed data eventually approved
Time-blocked train/validation/holdout, embargo overlaps and original-vintage release lags. Conduct matched policy replay, bootstrap by independent event block, monitor false discoveries across multiple choices, expose failed dates and liquidity drawdowns.
**Stop:** No stable out-of-sample cost-adjusted advantage over delivery-aware manual baseline at realistic pool eligibility..

## Cost and publication
Market depth and eligible pool inventory limit size; include bid/ask, delivery allocations, financing and clearing margin.
$180k assumed total 24m development/data/maintenance cost; assumed launch in month 6; assumed annual gross outcome downside/base/upside $0k/$130k/$260k. Resulting 24m net ROI **-100.0% / 8.3% / 116.7% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
Public papers and official datasets are context only, not replication. Any material positive result requires independently reproduced code + signed human review; no automatic trading.

## Acceptance gating
AC-001..AC-005 from SPEC each requires a runnable test record and model/data rights signoff. If source is incomplete, report a negative or blocked result, not a proxy alpha claim.
