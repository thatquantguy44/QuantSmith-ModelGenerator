# PLAN — US Municipal Credit Vulnerability to Local Insurance Withdrawal
**Status: proposed implementation architecture; not executed.**

## Research system
`legal-source-allowlist → release-version capture → us-muni-insurance-withdrawal-risk normalized state → Debt-to-revenue and issuer-rating-only spread screen → Geospatial panel DiD with insurance availability shock and issuer boundary crosswalk → economic replay → invariants + negative controls → independent research review`.

## Data contracts
County FEMA risk, EMMA issuer disclosures, municipal price quotes, property valuations, insurer exit/public rate filings
Record source version, unit, calendar/market timezone and initial public visibility. County/issuer boundary vintage and disclosure posting timestamp; FEMA risk version frozen at decision date.
Build synthetic datasets exercising both ordinary and adversarial cases before attempting licensed ingestion.

## Identification and modeling
- Start with `Debt-to-revenue and issuer-rating-only spread screen`; quantify human and market execution capacity honestly.
- Candidate `Geospatial panel DiD with insurance availability shock and issuer boundary crosswalk` is estimated on predeclared training windows and evaluated only after hyperparameters frozen.
- Conditional advanced extension: Graph exposure propagation into municipal tax receipts with heterogeneous hazard risk; justify its added parameters and risks through a paired ablation.
- Critical identification concern: FEMA risk baseline old; climate model not equivalent to observed insurance withdrawal; selective municipal disclosure.
- Implementation economics: Muni bonds illiquid, spread carry/horizon may exceed signal; favor risk-monitoring before trading.

## Interfaces (proposed, not present)
`source.load(license,as_of)`, `contract.normalize(records,clock)`, `baseline.solve(states)`, `candidate.solve(states)`, `econ.replay(actions,quotes)`, `evals.falsify()`.
Use the same eligible universe and cost model for both actions, preserve rejection/failure traces, and prohibit false retrospective model availability.

## Requirement/task traceability
REQ-001→T-01,T-02; REQ-002→T-03; REQ-003→T-04,T-05; REQ-004→T-06; NFR-001/NFR-002→T-02,T-07.
**Decision gate:** No incremental out-of-time predictive effect after socioeconomic covariates and issuer-selection controls.
The implementation is BLOCKED until source rights, timestamps and economic costs are accepted.
