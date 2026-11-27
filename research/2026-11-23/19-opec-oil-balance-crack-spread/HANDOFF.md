# HANDOFF — OPEC Oil Balance Residuals and Refined Crack-Spread Transmission
**Status:** research design delivered, **all empirical and executable work BLOCKED/not started**. Owner, legal reviewer and dataset approver: not assigned.

## Transfer to implementing researcher
**Economic decision:** Hedge product crack spreads when public crude production and stock-flow residuals imply inventory stress.
**Falsifiable claim:** JODI stock-flow residuals after publication improve future refined crack-spread risk forecasts over oil price and seasonal inventories.
**First deliverable:** synthetic/point-in-time fixture and reproducible `Seasonal EIA weekly inventories and oil curve`.
**Then:** Constrained oil balance reconciliation and local-projection crack spread model.
**Stop:** Residual predictive content disappears after vintages, shipping lags and front-month liquidity adjustment..

## Required unresolved inputs
- Licence and historical access for ICE/NYMEX refined product and crude futures settlement histories.
- Exact public timestamp/version contract: JODI typically publishes next-month and revises; align release date, not reporting month; execute only after release.
- Authorized reference data (never to GitHub): Approved energy derivatives trade limits/costs.
- Correct edge treatment: Monthly country submission corrections, unit conversion mismatches and sanctioned flow missingness..
- Realizable economics: Use executable refined product futures, contract rolls, inventory and liquidity spreads; no inference from paper spreads..

## Reproducibility
Pin source URL/version/time, commit, configuration hash, calendar, random seed, solver tolerance, excluded instrument list and holdout. Preserve failed/negative tests, claims and uncertainty.

## Financial scope
$170k assumed total 24m development/data/maintenance cost; assumed launch in month 7; assumed annual gross outcome downside/base/upside $0k/$115k/$280k. Resulting 24m net ROI **-100.0% / -4.2% / 133.3% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
Scores and sensitivities are design judgments, not alpha or observed savings. Reviewer must explicitly accept evidence before moving to shadow mode.
