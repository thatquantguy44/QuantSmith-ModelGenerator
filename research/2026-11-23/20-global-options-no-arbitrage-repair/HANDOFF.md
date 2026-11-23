# HANDOFF — Arbitrage-Free Equity Volatility Surface Repair Across Markets
**Status:** research design delivered, **all empirical and executable work BLOCKED/not started**. Owner, legal reviewer and dataset approver: not assigned.

## Transfer to implementing researcher
**Economic decision:** Produce arbitrage-consistent option risk surfaces and screen put-call/calendar violations before risk budgeting.
**Falsifiable claim:** Constrained surface repair reduces downstream hedge Greeks error and false arbitrage alarms versus independent spline fitting.
**First deliverable:** synthetic/point-in-time fixture and reproducible `Per-expiry unconstrained cubic interpolation with clip to bid/ask`.
**Then:** Static no-arbitrage SVI/SSVI constrained calibration with conservative quote filters.
**Stop:** Constrained repair does not reduce out-of-sample pricing/hedging error or introduces hidden quote crossings..

## Required unresolved inputs
- Licence and historical access for Licensed cross-exchange historical option chains, forward curves and bid-ask depths.
- Exact public timestamp/version contract: Quote timestamp aligned to each exchange session; repair uses no quotes from future or closed-market snapshots.
- Authorized reference data (never to GitHub): Approved option market-making Greeks and trade limits.
- Correct edge treatment: American vs European option styles, dividend marks, early exercise, restricted historical quote rights..
- Realizable economics: Surface repairs support quality/risk decisions first; apparent arbitrage cannot be traded without depth and cost..

## Reproducibility
Pin source URL/version/time, commit, configuration hash, calendar, random seed, solver tolerance, excluded instrument list and holdout. Preserve failed/negative tests, claims and uncertainty.

## Financial scope
$185k assumed total 24m development/data/maintenance cost; assumed launch in month 8; assumed annual gross outcome downside/base/upside $0k/$105k/$265k. Resulting 24m net ROI **-100.0% / -24.3% / 91.0% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
Scores and sensitivities are design judgments, not alpha or observed savings. Reviewer must explicitly accept evidence before moving to shadow mode.
