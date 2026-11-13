# EVALS — Treasury Clearing Access-Path & Duplicate-Margin Optimizer
**Status:** Design for tests, no experiment performed.

## Economic claim and comparator
- **H1:** Path-aware margin, clearing fees and funding costs change the optimal routing mix and reduce total economically consumed liquidity relative to selecting the lowest quoted repo rate.
- **Comparator:** Minimize executable repo rate ignoring path-specific costs, after validating that every route is eligible..
- **Candidate:** Mixed-integer convex routing with separate margin, settlement and liquidity shadow prices..
- **Advanced alternative:** Stochastic two-stage CCP-margin and default-fund planning with cross-netting robustness..
- **Metrics:** USD all-in funding cost, dollar liquidity encumbrance, margin stress p99, ineligible route count, rejection rate..
- **Stop/no-go:** Reject if simulated net savings are below 2 bps of affected financing notional or vanish under independently validated margin rules.
- **Cost sensitivity:** USD $280k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $160k–$620k over 24 months. Net ROI = (gross benefit − cost)/cost = **-43% to 121%**. NOT forecast or historical measurement. Economic lever: assume 2–8 bps avoidable total cost on an eligible hypothetical $250m continuously financed at ~1yr equivalent and fraction of volume attainable; capture model must account for actual turnover.

## Evaluation splits and safeguards
1. Set chronologically non-overlapping training, validation and holdout periods; embargo trades with outcome windows crossing splits.
2. Align all records to first permitted information availability, not economic reference date. trade routing decision at quote acceptance; historical public aggregates are lagged and cannot be used as intraday quotes
3. Use exactly matched feasible opportunity sets and complete funding, execution, regulatory and operational frictions for baseline/candidate.
4. Compare against **no-action** when the cost of the position or data is not measurable.
5. Use time-blocked paired bootstrap uncertainty, relevant alternative market regimes and explicit multiple-hypothesis correction.
6. Test adverse implementation constraints: Constrained by FICC participant access, available repo quote depth, account/entity eligibility and netting-set segregation.
7. Stress identification risk: Clearing rule exemptions and netting eligibility vary; estimated margin offsets could be nonportable across entities.
8. Record both gross and net metrics; a statistically significant signal is not necessarily profitable or operationally feasible.

## Specific negative/invariant tests
non-additive netting; no double counting of margin credit; affiliate segregation; stressed CCLF depletion.

## Shadow mode and production gate
AC-001–AC-005 need test evidence and reproducible run envelopes. No trading or execution without human risk and legal approval; where public proxies are insufficient, block P&L claims and publish only a risk-monitoring exploratory result. The accepted outcome may be **negative** and should remain in the research archive.
