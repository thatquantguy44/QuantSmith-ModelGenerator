# HANDOFF — Corporate Bond Securities Lending from CDS Basis Hedge Demand
**Status:** research design delivered, **all empirical and executable work BLOCKED/not started**. Owner, legal reviewer and dataset approver: not assigned.

## Transfer to implementing researcher
**Economic decision:** Allocate bond lending supply to CDS-bond basis hedging demand with counterparty and liquidity limits.
**Falsifiable claim:** CDS-bond basis dislocations predict incremental observable bond borrowing demand after conditioning on issue float, liquidity and credit stress.
**First deliverable:** synthetic/point-in-time fixture and reproducible `Trailing borrower request count and issue-size utilization`.
**Then:** Matched event study plus borrow-arrival hazard conditional on CDS-bond basis.
**Stop:** Estimated basis effects fail paired holdouts or increase rejected locates after slippage and liquidity controls..

## Required unresolved inputs
- Licence and historical access for Corporate bond TRACE histories, CDS quotes and bond lending locates.
- Exact public timestamp/version contract: CDS and cash-bond spreads only after published executable quote times; lending fills observed subsequently.
- Authorized reference data (never to GitHub): Permissioned borrower requests/loan data.
- Correct edge treatment: Non-executable CDS quotes, bond TRACE delay and endogeneity of credit distress..
- Realizable economics: Bond borrow capacity and transaction costs can overwhelm narrow basis; never equate public volume with tradable borrow..

## Reproducibility
Pin source URL/version/time, commit, configuration hash, calendar, random seed, solver tolerance, excluded instrument list and holdout. Preserve failed/negative tests, claims and uncertainty.

## Financial scope
$150k assumed total 24m development/data/maintenance cost; assumed launch in month 7; assumed annual gross outcome downside/base/upside $0k/$110k/$230k. Resulting 24m net ROI **-100.0% / 3.9% / 117.2% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
Scores and sensitivities are design judgments, not alpha or observed savings. Reviewer must explicitly accept evidence before moving to shadow mode.
