# HANDOFF — Biotech FDA Catalyst Probability versus Options Event Premium
**Status:** research design delivered, **all empirical and executable work BLOCKED/not started**. Owner, legal reviewer and dataset approver: not assigned.

## Transfer to implementing researcher
**Economic decision:** Test whether equity option implied event moves overstate conditional post-decision realized jumps at fixed risk limits.
**Falsifiable claim:** Official pre-event regulatory state improves risk-adjusted event-volatility pricing relative to a generic historical event move.
**First deliverable:** synthetic/point-in-time fixture and reproducible `Historical absolute event returns grouped by market cap and indication`.
**Then:** Regulatory-document event taxonomy + shrinkage conditional jump model.
**Stop:** Conditional probability model fails event-matched calibration or net executable option premium..

## Required unresolved inputs
- Licence and historical access for OptionMetrics/OPRA historical executable bid-ask quotes.
- Exact public timestamp/version contract: No use of FDA outcome until public approval announcement; option quotes at last feasible pre-event time.
- Authorized reference data (never to GitHub): Approved derivatives margin and short-option risk limits.
- Correct edge treatment: FDA database daily updates can lag original approval; sample selection, delistings and halted option quotes..
- Realizable economics: Biotech option spreads and gap risk severe; define small budget and loss limit before evaluating..

## Reproducibility
Pin source URL/version/time, commit, configuration hash, calendar, random seed, solver tolerance, excluded instrument list and holdout. Preserve failed/negative tests, claims and uncertainty.

## Financial scope
$195k assumed total 24m development/data/maintenance cost; assumed launch in month 9; assumed annual gross outcome downside/base/upside $0k/$110k/$295k. Resulting 24m net ROI **-100.0% / -29.5% / 89.1% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
Scores and sensitivities are design judgments, not alpha or observed savings. Reviewer must explicitly accept evidence before moving to shadow mode.
