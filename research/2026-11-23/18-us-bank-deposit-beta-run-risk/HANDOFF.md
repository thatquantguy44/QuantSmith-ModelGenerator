# HANDOFF — US Bank Deposit Beta and Mark-to-Market Securities Run Risk
**Status:** research design delivered, **all empirical and executable work BLOCKED/not started**. Owner, legal reviewer and dataset approver: not assigned.

## Transfer to implementing researcher
**Economic decision:** Assess which banks face funding-cost and securities-loss convexity under uninsured deposit migration.
**Falsifiable claim:** A joint deposit-beta and securities mark-to-market gap predicts earnings/credit deterioration better than uninsured deposit percentage.
**First deliverable:** synthetic/point-in-time fixture and reproducible `Uninsured deposit share plus book capital ratio`.
**Then:** Hierarchical deposit beta estimation plus accounting-based duration stress.
**Stop:** No incremental forecast versus capital/deposit mix baseline after strict public release lag..

## Required unresolved inputs
- Licence and historical access for Bank funding rate panels and credit spread datasets.
- Exact public timestamp/version contract: Quarter-end balances become usable only at the first public Call Report publication, not period end.
- Authorized reference data (never to GitHub): Authorized bank exposures, no private depositor/account data.
- Correct edge treatment: Quarterly revisions, mergers, bank survivorship and missing bank-specific deposit pricing..
- Realizable economics: Large regional bank equity/cash bonds viable; small banks thin, CDS pricing inaccessible and not required for public proxy..

## Reproducibility
Pin source URL/version/time, commit, configuration hash, calendar, random seed, solver tolerance, excluded instrument list and holdout. Preserve failed/negative tests, claims and uncertainty.

## Financial scope
$155k assumed total 24m development/data/maintenance cost; assumed launch in month 6; assumed annual gross outcome downside/base/upside $0k/$120k/$245k. Resulting 24m net ROI **-100.0% / 16.1% / 137.1% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
Scores and sensitivities are design judgments, not alpha or observed savings. Reviewer must explicitly accept evidence before moving to shadow mode.
