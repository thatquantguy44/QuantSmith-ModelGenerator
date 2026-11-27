# EVALS — US Bank Deposit Beta and Mark-to-Market Securities Run Risk
**No empirical test run. Evaluation design, not evidence.**

## H1/H0 and economics
H1: A joint deposit-beta and securities mark-to-market gap predicts earnings/credit deterioration better than uninsured deposit percentage.
H0: the feasible `Uninsured deposit share plus book capital ratio` benchmark is not improved net of risk/cost.
Candidate: `Hierarchical deposit beta estimation plus accounting-based duration stress`. Advanced: Agent-based depositor migration with liquidity haircut and contagion sensitivity
Metrics: Next-quarter NII loss, downside rank precision, capital shortfall, sector-neutral return IC.

## Mandatory synthetic invariants
- `available_at_utc <= decision_time`, calendar/session alignment and source-version hash.
- Feasible decision constraints match: NII_i≈Loans_i*r_L - Deposits_i*(r_D0+β_i*Δr) - Wholesale_i*r_W ; StressGap_i=HTMLoss_i+RunOutflow_i*FundingSpread.
- Units and payable/receivable cash direction from: β_i deposit repricing elasticity, HTMLoss published held-to-maturity unrealized loss proxy, RunOutflow scenario.
- True negative controls: Quarterly revisions, mergers, bank survivorship and missing bank-specific deposit pricing.
- Equal event/asset universe, quoted bid/ask, capacity and no-action alternatives.

## Empirical design if licensed data eventually approved
Time-blocked train/validation/holdout, embargo overlaps and original-vintage release lags. Conduct matched policy replay, bootstrap by independent event block, monitor false discoveries across multiple choices, expose failed dates and liquidity drawdowns.
**Stop:** No incremental forecast versus capital/deposit mix baseline after strict public release lag..

## Cost and publication
Large regional bank equity/cash bonds viable; small banks thin, CDS pricing inaccessible and not required for public proxy.
$155k assumed total 24m development/data/maintenance cost; assumed launch in month 6; assumed annual gross outcome downside/base/upside $0k/$120k/$245k. Resulting 24m net ROI **-100.0% / 16.1% / 137.1% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
Public papers and official datasets are context only, not replication. Any material positive result requires independently reproduced code + signed human review; no automatic trading.

## Acceptance gating
AC-001..AC-005 from SPEC each requires a runnable test record and model/data rights signoff. If source is incomplete, report a negative or blocked result, not a proxy alpha claim.
