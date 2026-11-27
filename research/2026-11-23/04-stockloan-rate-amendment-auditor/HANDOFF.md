# HANDOFF — Securities Loan Retroactive Rate Amendment Revenue Assurance
**Status:** research design delivered, **all empirical and executable work BLOCKED/not started**. Owner, legal reviewer and dataset approver: not assigned.

## Transfer to implementing researcher
**Economic decision:** Identify contractually unsupported retroactive fee amendments before invoice posting.
**Falsifiable claim:** Bitemporal contract-and-loan event reconstruction detects more true billing exceptions than end-of-day price reconciliation without increasing false disputes.
**First deliverable:** synthetic/point-in-time fixture and reproducible `Latest agreed fee × end-period balance × elapsed days`.
**Then:** Bitemporal finite-state rate and loan lifecycle ledger with invariant checks.
**Stop:** No improvement in high-severity seeded exceptions relative to deterministic ledger, or unauthorized dispute actions..

## Required unresolved inputs
- Licence and historical access for Commercial corporate actions, loan accounting system documentation.
- Exact public timestamp/version contract: Invoice run includes only fee amendments authorized and received before invoice cut-off, even if effective date is earlier.
- Authorized reference data (never to GitHub): Loan confirmations, fee invoices, counterparty agreements under strict access.
- Correct edge treatment: Contract-level bilateral waiver rules, fee confirmation ambiguity and out-of-order event feeds..
- Realizable economics: Value in avoided losses and less manual rework, not trading alpha; false dispute costs and review minutes cap benefit..

## Reproducibility
Pin source URL/version/time, commit, configuration hash, calendar, random seed, solver tolerance, excluded instrument list and holdout. Preserve failed/negative tests, claims and uncertainty.

## Financial scope
$105k assumed total 24m development/data/maintenance cost; assumed launch in month 4; assumed annual gross outcome downside/base/upside $0k/$95k/$165k. Resulting 24m net ROI **-100.0% / 50.8% / 161.9% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
Scores and sensitivities are design judgments, not alpha or observed savings. Reviewer must explicitly accept evidence before moving to shadow mode.
