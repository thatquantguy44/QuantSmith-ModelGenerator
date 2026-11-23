# EVALS — Corporate Bond Securities Lending from CDS Basis Hedge Demand
**No empirical test run. Evaluation design, not evidence.**

## H1/H0 and economics
H1: CDS-bond basis dislocations predict incremental observable bond borrowing demand after conditioning on issue float, liquidity and credit stress.
H0: the feasible `Trailing borrower request count and issue-size utilization` benchmark is not improved net of risk/cost.
Candidate: `Matched event study plus borrow-arrival hazard conditional on CDS-bond basis`. Advanced: Structural joint CDS/bond market-maker inventory model with selection-corrected demand
Metrics: Borrow-arrival log score, realized net fee improvement, stale quote rate and borrow supply capacity.

## Mandatory synthetic invariants
- `available_at_utc <= decision_time`, calendar/session alignment and source-version hash.
- Feasible decision constraints match: E[BorrowDemand_{i,t+1}|F_t]=f(Basis_{i,t},Float_i,Liquidity_{i,t}); max_q Σ_i q_i*(fee_i - failCost_i) with q_i≤available_i.
- Units and payable/receivable cash direction from: Basis=CDS spread minus matched cash-bond spread; q_i is feasible bond loan notional; borrower behavior must be estimated.
- True negative controls: Non-executable CDS quotes, bond TRACE delay and endogeneity of credit distress.
- Equal event/asset universe, quoted bid/ask, capacity and no-action alternatives.

## Empirical design if licensed data eventually approved
Time-blocked train/validation/holdout, embargo overlaps and original-vintage release lags. Conduct matched policy replay, bootstrap by independent event block, monitor false discoveries across multiple choices, expose failed dates and liquidity drawdowns.
**Stop:** Estimated basis effects fail paired holdouts or increase rejected locates after slippage and liquidity controls..

## Cost and publication
Bond borrow capacity and transaction costs can overwhelm narrow basis; never equate public volume with tradable borrow.
$150k assumed total 24m development/data/maintenance cost; assumed launch in month 7; assumed annual gross outcome downside/base/upside $0k/$110k/$230k. Resulting 24m net ROI **-100.0% / 3.9% / 117.2% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
Public papers and official datasets are context only, not replication. Any material positive result requires independently reproduced code + signed human review; no automatic trading.

## Acceptance gating
AC-001..AC-005 from SPEC each requires a runnable test record and model/data rights signoff. If source is incomplete, report a negative or blocked result, not a proxy alpha claim.
