# HANDOFF — European Interconnector Congestion Power-Spread State Estimator
**Status:** research design delivered, **all empirical and executable work BLOCKED/not started**. Owner, legal reviewer and dataset approver: not assigned.

## Transfer to implementing researcher
**Economic decision:** Select hedged cross-zone power spread exposures conditional on public transfer constraints.
**Falsifiable claim:** Transmission-capacity-corrected congestion states improve next-day risk classification and hedge calibration versus load-only spread models.
**First deliverable:** synthetic/point-in-time fixture and reproducible `Historical seasonal hourly spread by zone pair`.
**Then:** Physical-congestion regime HMM with capacity-constrained exposure mapper.
**Stop:** Spread gains disappear after simultaneous public forecast access, congestion settlement and capacity rights..

## Required unresolved inputs
- Licence and historical access for Executable EPEX/ICE forward curves and interconnector rights prices.
- Exact public timestamp/version contract: Only ENTSO-E forecasts published before day-ahead bidding deadline; actual flows/prices are evaluation targets.
- Authorized reference data (never to GitHub): Permissioned utility node positions and hedging restrictions.
- Correct edge treatment: Cross-zone transmission rights and operational capacities not freely tradable; timestamps and price revisions..
- Realizable economics: Transmission rights/market access and collateral requirements dominate quoted spread opportunities..

## Reproducibility
Pin source URL/version/time, commit, configuration hash, calendar, random seed, solver tolerance, excluded instrument list and holdout. Preserve failed/negative tests, claims and uncertainty.

## Financial scope
$220k assumed total 24m development/data/maintenance cost; assumed launch in month 9; assumed annual gross outcome downside/base/upside $0k/$150k/$355k. Resulting 24m net ROI **-100.0% / -14.8% / 101.7% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
Scores and sensitivities are design judgments, not alpha or observed savings. Reviewer must explicitly accept evidence before moving to shadow mode.
