# HANDOFF — Agency MBS Dollar-Roll Cheapest-to-Deliver Financing Option
**Status:** research design delivered, **all empirical and executable work BLOCKED/not started**. Owner, legal reviewer and dataset approver: not assigned.

## Transfer to implementing researcher
**Economic decision:** Select TBA dollar-roll financing and permissible pool delivery sets versus holding specified pools financed through repo.
**Falsifiable claim:** Explicit deliverability and pool opportunity costs explain dollar-roll implied funding differences beyond coupon, term and simple financing spreads.
**First deliverable:** synthetic/point-in-time fixture and reproducible `Dollar-roll implied financing vs same-tenor generic repo without delivery-option valuation`.
**Then:** Constrained pool-delivery optimizer with observable pool financing carry and roll prices.
**Stop:** No stable out-of-sample cost-adjusted advantage over delivery-aware manual baseline at realistic pool eligibility..

## Required unresolved inputs
- Licence and historical access for Executable TBA rolls, specified-pool prices, MBS prepayment factors.
- Exact public timestamp/version contract: Decision at pre-roll executable quote; EPN pool assignment becomes known later and must not leak into earlier signals.
- Authorized reference data (never to GitHub): Approved pool inventory, counterparties and EPN allocations; never commit actual records.
- Correct edge treatment: Pool price selection, payup optionality, actual pool availability and post-trade EPN leakage..
- Realizable economics: Market depth and eligible pool inventory limit size; include bid/ask, delivery allocations, financing and clearing margin..

## Reproducibility
Pin source URL/version/time, commit, configuration hash, calendar, random seed, solver tolerance, excluded instrument list and holdout. Preserve failed/negative tests, claims and uncertainty.

## Financial scope
$180k assumed total 24m development/data/maintenance cost; assumed launch in month 6; assumed annual gross outcome downside/base/upside $0k/$130k/$260k. Resulting 24m net ROI **-100.0% / 8.3% / 116.7% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
Scores and sensitivities are design judgments, not alpha or observed savings. Reviewer must explicitly accept evidence before moving to shadow mode.
