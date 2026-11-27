# HANDOFF — CCP Member Default Position-Porting Time and Liquidity Optimization
**Status:** research design delivered, **all empirical and executable work BLOCKED/not started**. Owner, legal reviewer and dataset approver: not assigned.

## Transfer to implementing researcher
**Economic decision:** Choose contingent porting routes and liquidity reserves for a hypothetical clearing-member default.
**Falsifiable claim:** A capacity-constrained porting algorithm lowers simulated liquidation shortfall and time-to-restore relative to static member choice.
**First deliverable:** synthetic/point-in-time fixture and reproducible `Manual first-available eligible clearing member routing`.
**Then:** Multi-period mixed-integer stochastic porting/survival flow simulator.
**Stop:** No improvement in adverse default scenarios over conservative porting alternatives or reliance on forbidden client position data..

## Required unresolved inputs
- Licence and historical access for Clearing member cost/risk reference agreements.
- Exact public timestamp/version contract: Use rule versions effective on default scenario date, exclude assumptions from later CCP notices.
- Authorized reference data (never to GitHub): Strictly permissioned client margin/porting agreements.
- Correct edge treatment: Actual CCP porting legality and bilateral customer consents unknown, correlated failures may be unidentifiable..
- Realizable economics: Not a deployable CCP recovery plan; scenario policy must be vetted by legal and risk..

## Reproducibility
Pin source URL/version/time, commit, configuration hash, calendar, random seed, solver tolerance, excluded instrument list and holdout. Preserve failed/negative tests, claims and uncertainty.

## Financial scope
$210k assumed total 24m development/data/maintenance cost; assumed launch in month 10; assumed annual gross outcome downside/base/upside $0k/$95k/$330k. Resulting 24m net ROI **-100.0% / -47.2% / 83.3% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
Scores and sensitivities are design judgments, not alpha or observed savings. Reviewer must explicitly accept evidence before moving to shadow mode.
