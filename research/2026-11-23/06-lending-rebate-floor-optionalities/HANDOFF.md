# HANDOFF — Securities Lending Cash Rebate Floor Optionality in Low-Rate Regimes
**Status:** research design delivered, **all empirical and executable work BLOCKED/not started**. Owner, legal reviewer and dataset approver: not assigned.

## Transfer to implementing researcher
**Economic decision:** Price and hedge rebate-floor optionality embedded in cash-collateral loan agreements.
**Falsifiable claim:** Contract-aware nonlinear floor valuation reduces forecast carry error and improper pricing vs linear spread assumptions.
**First deliverable:** synthetic/point-in-time fixture and reproducible `Static contractual rebate minus benchmark with no optionality`.
**Then:** Rate-tree floor valuation and curve calibration with contract clause parser.
**Stop:** Valuation adds no meaningful incremental pricing accuracy to conservative quoted-fee schedules..

## Required unresolved inputs
- Licence and historical access for OIS curves and vol surfaces with redistribution rights.
- Exact public timestamp/version contract: Valuation at contract initiation using curve observed by quote cut-off, not future realized policy rates.
- Authorized reference data (never to GitHub): Permissioned cash rebate agreements and collateral balances.
- Correct edge treatment: Floor rights and term structures vary by legal agreement; historic negative-rate regimes have sample limitations..
- Realizable economics: Profit only if floors contractually negotiated; hedge notional and floor illiquidity restrict scale..

## Reproducibility
Pin source URL/version/time, commit, configuration hash, calendar, random seed, solver tolerance, excluded instrument list and holdout. Preserve failed/negative tests, claims and uncertainty.

## Financial scope
$135k assumed total 24m development/data/maintenance cost; assumed launch in month 7; assumed annual gross outcome downside/base/upside $0k/$80k/$225k. Resulting 24m net ROI **-100.0% / -16.0% / 136.1% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
Scores and sensitivities are design judgments, not alpha or observed savings. Reviewer must explicitly accept evidence before moving to shadow mode.
