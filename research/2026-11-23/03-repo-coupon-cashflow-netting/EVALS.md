# EVALS — Repo Coupon and Principal Event Cash-Flow Netting Scheduler
**No empirical test run. Evaluation design, not evidence.**

## H1/H0 and economics
H1: Event-aware legally permissible netting reduces liquidity buffer and operational exceptions versus cash-flow-independent settlement.
H0: the feasible `Gross independent payment processing with static buffer` benchmark is not improved net of risk/cost.
Candidate: `Mixed-integer liquidity scheduling with eligibility/netting-set constraints`. Advanced: Stochastic event-flow MPC with missed payment penalties and legal-entity netting restrictions
Metrics: Peak cash buffer, gross payment count, exception cost, settlement timeliness.

## Mandatory synthetic invariants
- `available_at_utc <= decision_time`, calendar/session alignment and source-version hash.
- Feasible decision constraints match: min_{f_{ij,t},B_t} Σ_t (c_B*B_t+c_F*|f_t|) s.t. Cash_t + B_t + inflow_t - outflow_t ≥0; NettingSet_{ij}=1.
- Units and payable/receivable cash direction from: f_ij,t are settlement payment flows; B_t is funding buffer; NettingSet is legal contractual binary.
- True negative controls: Wrong beneficial-ownership treatment, netting rights and special cash settlement terms.
- Equal event/asset universe, quoted bid/ask, capacity and no-action alternatives.

## Empirical design if licensed data eventually approved
Time-blocked train/validation/holdout, embargo overlaps and original-vintage release lags. Conduct matched policy replay, bootstrap by independent event block, monitor false discoveries across multiple choices, expose failed dates and liquidity drawdowns.
**Stop:** No capacity-adjusted cost reduction versus pre-netted conventional operations or violations of payment rights..

## Cost and publication
Savings limited to payments legally eligible for netting; reconciliation costs, daylight overdraft fees and solver latency included.
$120k assumed total 24m development/data/maintenance cost; assumed launch in month 5; assumed annual gross outcome downside/base/upside $0k/$95k/$190k. Resulting 24m net ROI **-100.0% / 25.3% / 150.7% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
Public papers and official datasets are context only, not replication. Any material positive result requires independently reproduced code + signed human review; no automatic trading.

## Acceptance gating
AC-001..AC-005 from SPEC each requires a runnable test record and model/data rights signoff. If source is incomplete, report a negative or blocked result, not a proxy alpha claim.
