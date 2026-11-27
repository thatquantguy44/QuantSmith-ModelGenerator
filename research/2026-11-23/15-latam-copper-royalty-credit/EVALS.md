# EVALS — Chile–Peru Copper Royalty Shock to Sovereign and Mining Credit
**No empirical test run. Evaluation design, not evidence.**

## H1/H0 and economics
H1: Legislated effective marginal royalty changes predict issuer-versus-sovereign credit spread dispersion beyond copper returns.
H0: the feasible `Copper price beta plus sovereign spread changes` benchmark is not improved net of risk/cost.
Candidate: `Event study with cross-sectional mine exposure and staggered law timing`. Advanced: Partial equilibrium mine-option tax model under investment deferral and country sovereign budget feedback
Metrics: Event abnormal spread, FX-adjusted carry, political timing placebo, credit risk attribution.

## Mandatory synthetic invariants
- `available_at_utc <= decision_time`, calendar/session alignment and source-version hash.
- Feasible decision constraints match: ΔSpread_{i,t+h}=β*Exposure_i*ΔRoyaltyRate_t+θ*ΔCopperPrice_t+γ'X_i,t+ε.
- Units and payable/receivable cash direction from: Exposure_i public geographic mine revenue, ΔRoyaltyRate legislated effective tax not mere bill proposal.
- True negative controls: Anticipatory legislative pricing, issuer/sov high correlations, illiquid local bond prices.
- Equal event/asset universe, quoted bid/ask, capacity and no-action alternatives.

## Empirical design if licensed data eventually approved
Time-blocked train/validation/holdout, embargo overlaps and original-vintage release lags. Conduct matched policy replay, bootstrap by independent event block, monitor false discoveries across multiple choices, expose failed dates and liquidity drawdowns.
**Stop:** No holdout effect after commodity beta and country shock controls or cannot identify legal effective date..

## Cost and publication
Bid/ask for mining credits and FX may swamp basis; avoid assuming continuous trading around policy announcements.
$170k assumed total 24m development/data/maintenance cost; assumed launch in month 8; assumed annual gross outcome downside/base/upside $0k/$95k/$260k. Resulting 24m net ROI **-100.0% / -25.5% / 103.9% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
Public papers and official datasets are context only, not replication. Any material positive result requires independently reproduced code + signed human review; no automatic trading.

## Acceptance gating
AC-001..AC-005 from SPEC each requires a runnable test record and model/data rights signoff. If source is incomplete, report a negative or blocked result, not a proxy alpha claim.
