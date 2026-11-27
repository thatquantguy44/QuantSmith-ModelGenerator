# PLAN — OPEC Oil Balance Residuals and Refined Crack-Spread Transmission
**Status: proposed implementation architecture; not executed.**

## Research system
`legal-source-allowlist → release-version capture → opec-oil-balance-crack-spread normalized state → Seasonal EIA weekly inventories and oil curve → Constrained oil balance reconciliation and local-projection crack spread model → economic replay → invariants + negative controls → independent research review`.

## Data contracts
JODI monthly crude stocks/flows, OPEC reports, EIA refinery/product balances, crack-futures settlements
Record source version, unit, calendar/market timezone and initial public visibility. JODI typically publishes next-month and revises; align release date, not reporting month; execute only after release.
Build synthetic datasets exercising both ordinary and adversarial cases before attempting licensed ingestion.

## Identification and modeling
- Start with `Seasonal EIA weekly inventories and oil curve`; quantify human and market execution capacity honestly.
- Candidate `Constrained oil balance reconciliation and local-projection crack spread model` is estimated on predeclared training windows and evaluated only after hyperparameters frozen.
- Conditional advanced extension: Multi-region Bayesian trade flow accounting with measurement error and shipping lags; justify its added parameters and risks through a paired ablation.
- Critical identification concern: Monthly country submission corrections, unit conversion mismatches and sanctioned flow missingness.
- Implementation economics: Use executable refined product futures, contract rolls, inventory and liquidity spreads; no inference from paper spreads.

## Interfaces (proposed, not present)
`source.load(license,as_of)`, `contract.normalize(records,clock)`, `baseline.solve(states)`, `candidate.solve(states)`, `econ.replay(actions,quotes)`, `evals.falsify()`.
Use the same eligible universe and cost model for both actions, preserve rejection/failure traces, and prohibit false retrospective model availability.

## Requirement/task traceability
REQ-001→T-01,T-02; REQ-002→T-03; REQ-003→T-04,T-05; REQ-004→T-06; NFR-001/NFR-002→T-02,T-07.
**Decision gate:** Residual predictive content disappears after vintages, shipping lags and front-month liquidity adjustment.
The implementation is BLOCKED until source rights, timestamps and economic costs are accepted.
