# EVALS — Regulatory LCR/NSFR Shadow Cost of Secured Funding Collateral
**No empirical test run. Evaluation design, not evidence.**

## H1/H0 and economics
H1: Dual-priced LCR/NSFR constraints reorder feasible funding selections and improve all-in liquidity-adjusted economics versus spread ranking.
H0: the feasible `Rank repo offers by quoted rate subject to gross notional limits` benchmark is not improved net of risk/cost.
Candidate: `Linear/mixed-integer secured funding allocation with LCR/NSFR dual-price attribution`. Advanced: Scenario-based shadow-price frontier with intraday and quarter-end liquidity risk
Metrics: All-in liquidity-adjusted cost, marginal dual price, buffer breaches, sensitivity to rule version.

## Mandatory synthetic invariants
- `available_at_utc <= decision_time`, calendar/session alignment and source-version hash.
- Feasible decision constraints match: min_x Σ_i (r_i*x_i + k_i*x_i) subject to HQLA_out/HQLA_in≥LCR_min and ASF(x)/RSF(x)≥NSFR_min, Σ_i x_i≥Need.
- Units and payable/receivable cash direction from: x_i secured funding quantities, k_i legal balance-sheet charge; LCR, ASF, RSF use approved regulatory definitions.
- True negative controls: Entity-specific regulatory implementation and internal forecasts differ; cannot reconstruct actual LCR from public totals.
- Equal event/asset universe, quoted bid/ask, capacity and no-action alternatives.

## Empirical design if licensed data eventually approved
Time-blocked train/validation/holdout, embargo overlaps and original-vintage release lags. Conduct matched policy replay, bootstrap by independent event block, monitor false discoveries across multiple choices, expose failed dates and liquidity drawdowns.
**Stop:** No cost difference over conservative liquidity-constrained benchmark or unstable/uninterpretable duals..

## Cost and publication
Use only approved internal regulatory measures when available; funding choices constrained by entity/collateral eligibility.
$180k assumed total 24m development/data/maintenance cost; assumed launch in month 8; assumed annual gross outcome downside/base/upside $0k/$120k/$280k. Resulting 24m net ROI **-100.0% / -11.1% / 107.4% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
Public papers and official datasets are context only, not replication. Any material positive result requires independently reproduced code + signed human review; no automatic trading.

## Acceptance gating
AC-001..AC-005 from SPEC each requires a runnable test record and model/data rights signoff. If source is incomplete, report a negative or blocked result, not a proxy alpha claim.
