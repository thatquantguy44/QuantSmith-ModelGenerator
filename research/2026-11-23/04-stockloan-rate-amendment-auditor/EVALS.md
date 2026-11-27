# EVALS — Securities Loan Retroactive Rate Amendment Revenue Assurance
**No empirical test run. Evaluation design, not evidence.**

## H1/H0 and economics
H1: Bitemporal contract-and-loan event reconstruction detects more true billing exceptions than end-of-day price reconciliation without increasing false disputes.
H0: the feasible `Latest agreed fee × end-period balance × elapsed days` benchmark is not improved net of risk/cost.
Candidate: `Bitemporal finite-state rate and loan lifecycle ledger with invariant checks`. Advanced: Probabilistic anomaly prioritization atop an exact contract-aware billing engine
Metrics: Synthetic exception precision/recall, manual hours, invoice basis-point leakage, false escalation rate.

## Mandatory synthetic invariants
- `available_at_utc <= decision_time`, calendar/session alignment and source-version hash.
- Feasible decision constraints match: Invoice_i=Σ_{d∈loanlife_i} Principal_{i,d} * Fee_{i,d} * DayFraction_d ; Error_i=Invoice_posted_i-Invoice_authorized_i.
- Units and payable/receivable cash direction from: Fee_i,d is effective authorized fee, distinct from late recorded amendment; Principal is open borrow notional.
- True negative controls: Contract-level bilateral waiver rules, fee confirmation ambiguity and out-of-order event feeds.
- Equal event/asset universe, quoted bid/ask, capacity and no-action alternatives.

## Empirical design if licensed data eventually approved
Time-blocked train/validation/holdout, embargo overlaps and original-vintage release lags. Conduct matched policy replay, bootstrap by independent event block, monitor false discoveries across multiple choices, expose failed dates and liquidity drawdowns.
**Stop:** No improvement in high-severity seeded exceptions relative to deterministic ledger, or unauthorized dispute actions..

## Cost and publication
Value in avoided losses and less manual rework, not trading alpha; false dispute costs and review minutes cap benefit.
$105k assumed total 24m development/data/maintenance cost; assumed launch in month 4; assumed annual gross outcome downside/base/upside $0k/$95k/$165k. Resulting 24m net ROI **-100.0% / 50.8% / 161.9% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
Public papers and official datasets are context only, not replication. Any material positive result requires independently reproduced code + signed human review; no automatic trading.

## Acceptance gating
AC-001..AC-005 from SPEC each requires a runnable test record and model/data rights signoff. If source is incomplete, report a negative or blocked result, not a proxy alpha claim.
