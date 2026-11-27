# TOOLING — US Municipal Credit Vulnerability to Local Insurance Withdrawal
**Status:** proposed modules and dependencies; none installed in this PR.

## Domain-specific potential packages
geopandas, statsmodels, duckdb, linearmodels. Pin exact compatible versions, lock hashes and document solver tolerances at implementation time; verify package licence and suitable model assumptions.

## Reusable cross-batch library contracts
- `qmg_core.sources.SnapshotSource.load(as_of, licence_class)`: original release and revision lineage.
- `qmg_core.time.AvailabilityIndex.filter(decision_time)`: no-later-than time filter.
- `qmg_core.contracts.EconomicState`: units, eligibility, `United States coastal, wildfire and flood-exposed municipal issuers` market calendar.
- `qmg_core.economics.CostModel`: Muni bonds illiquid, spread carry/horizon may exceed signal; favor risk-monitoring before trading.
- `qmg_core.baselines.PolicyComparator`: Debt-to-revenue and issuer-rating-only spread screen
- `qmg_core.evals.FalsificationGate`: No incremental out-of-time predictive effect after socioeconomic covariates and issuer-selection controls.
- `qmg_core.evidence.ClaimLedger`: verifiable external claims versus hypotheses.

## Project-specific package proposal
`src/qmg/research/us_muni_insurance_withdrawal_risk/`: `contracts.py`, `source_adapter.py`, `baseline.py`, `candidate.py`, `objective.py`, `evals.py`, `cli.py`, `tests/test_publication_clock.py`, `tests/test_negative_controls.py`.
Domain input: County FEMA risk, EMMA issuer disclosures, municipal price quotes, property valuations, insurer exit/public rate filings. Main model: Geospatial panel DiD with insurance availability shock and issuer boundary crosswalk. Optional next step: Graph exposure propagation into municipal tax receipts with heterogeneous hazard risk.

## Interface safety
Keep public/paid/private adapters separate; no token strings, client data or scrape-prohibited market data in the repository. Export proposed schema examples with **synthetic rows only**. Runtime and tests are not implemented.
