# EVALS — Arbitrage-Free Equity Volatility Surface Repair Across Markets
**No empirical test run. Evaluation design, not evidence.**

## H1/H0 and economics
H1: Constrained surface repair reduces downstream hedge Greeks error and false arbitrage alarms versus independent spline fitting.
H0: the feasible `Per-expiry unconstrained cubic interpolation with clip to bid/ask` benchmark is not improved net of risk/cost.
Candidate: `Static no-arbitrage SVI/SSVI constrained calibration with conservative quote filters`. Advanced: Joint multi-market neural stochastic volatility calibrated to arbitrage constraints and holidays
Metrics: Static arbitrage violations, held-out option price MAE, hedge delta error, false anomaly alerts.

## Mandatory synthetic invariants
- `available_at_utc <= decision_time`, calendar/session alignment and source-version hash.
- Feasible decision constraints match: min_{σ_surface} Σ_{k,T} w_{k,T}(σ_{k,T}-σ_mid)^2 + λ*Smooth(σ) s.t. ∂_T TotalVar≥0, ConvexCall(K,T)≥0.
- Units and payable/receivable cash direction from: k log-forward moneyness,T maturity; σ implied vol, w quote reliability; bounds depend on option exercise type.
- True negative controls: American vs European option styles, dividend marks, early exercise, restricted historical quote rights.
- Equal event/asset universe, quoted bid/ask, capacity and no-action alternatives.

## Empirical design if licensed data eventually approved
Time-blocked train/validation/holdout, embargo overlaps and original-vintage release lags. Conduct matched policy replay, bootstrap by independent event block, monitor false discoveries across multiple choices, expose failed dates and liquidity drawdowns.
**Stop:** Constrained repair does not reduce out-of-sample pricing/hedging error or introduces hidden quote crossings..

## Cost and publication
Surface repairs support quality/risk decisions first; apparent arbitrage cannot be traded without depth and cost.
$185k assumed total 24m development/data/maintenance cost; assumed launch in month 8; assumed annual gross outcome downside/base/upside $0k/$105k/$265k. Resulting 24m net ROI **-100.0% / -24.3% / 91.0% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
Public papers and official datasets are context only, not replication. Any material positive result requires independently reproduced code + signed human review; no automatic trading.

## Acceptance gating
AC-001..AC-005 from SPEC each requires a runnable test record and model/data rights signoff. If source is incomplete, report a negative or blocked result, not a proxy alpha claim.
