# EVALS — CCP Member Default Position-Porting Time and Liquidity Optimization
**No empirical test run. Evaluation design, not evidence.**

## H1/H0 and economics
H1: A capacity-constrained porting algorithm lowers simulated liquidation shortfall and time-to-restore relative to static member choice.
H0: the feasible `Manual first-available eligible clearing member routing` benchmark is not improved net of risk/cost.
Candidate: `Multi-period mixed-integer stochastic porting/survival flow simulator`. Advanced: Distributionally robust queueing network with correlated member liquidity and stress haircuts
Metrics: Porting completion by deadline, unmet margin, loss given port failure, rerouting overhead.

## Mandatory synthetic invariants
- `available_at_utc <= decision_time`, calendar/session alignment and source-version hash.
- Feasible decision constraints match: min_{x_{ij}} Σ_{ij} x_{ij}*(PortDelay_{ij}+λ*MarginShortfall_{ij}) subject to Σ_j x_{ij}≤Position_i, K_j≥Σ_i x_{ij}.
- Units and payable/receivable cash direction from: x_ij assigned position notional, K_j receiving-member capacity; only eligible clients/contracts included.
- True negative controls: Actual CCP porting legality and bilateral customer consents unknown, correlated failures may be unidentifiable.
- Equal event/asset universe, quoted bid/ask, capacity and no-action alternatives.

## Empirical design if licensed data eventually approved
Time-blocked train/validation/holdout, embargo overlaps and original-vintage release lags. Conduct matched policy replay, bootstrap by independent event block, monitor false discoveries across multiple choices, expose failed dates and liquidity drawdowns.
**Stop:** No improvement in adverse default scenarios over conservative porting alternatives or reliance on forbidden client position data..

## Cost and publication
Not a deployable CCP recovery plan; scenario policy must be vetted by legal and risk.
$210k assumed total 24m development/data/maintenance cost; assumed launch in month 10; assumed annual gross outcome downside/base/upside $0k/$95k/$330k. Resulting 24m net ROI **-100.0% / -47.2% / 83.3% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
Public papers and official datasets are context only, not replication. Any material positive result requires independently reproduced code + signed human review; no automatic trading.

## Acceptance gating
AC-001..AC-005 from SPEC each requires a runnable test record and model/data rights signoff. If source is incomplete, report a negative or blocked result, not a proxy alpha claim.
