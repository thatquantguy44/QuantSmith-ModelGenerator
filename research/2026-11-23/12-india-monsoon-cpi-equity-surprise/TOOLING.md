# TOOLING — India Monsoon Surprise to Food CPI and Local Equity Pricing
**Status:** proposed modules and dependencies; none installed in this PR.

## Domain-specific potential packages
xarray, geopandas, pymc, statsmodels. Pin exact compatible versions, lock hashes and document solver tolerances at implementation time; verify package licence and suitable model assumptions.

## Reusable cross-batch library contracts
- `qmg_core.sources.SnapshotSource.load(as_of, licence_class)`: original release and revision lineage.
- `qmg_core.time.AvailabilityIndex.filter(decision_time)`: no-later-than time filter.
- `qmg_core.contracts.EconomicState`: units, eligibility, `India, state agriculture, INR and Indian listed consumer equities` market calendar.
- `qmg_core.economics.CostModel`: Large liquid Indian stocks capacity feasible only with correct foreign-investor access, FX costs and exchange calendars.
- `qmg_core.baselines.PolicyComparator`: All-India seasonal rainfall deviation plus autoregressive food CPI
- `qmg_core.evals.FalsificationGate`: No incremental holdout inflation forecast or stock-return effect against rainfall benchmark.
- `qmg_core.evidence.ClaimLedger`: verifiable external claims versus hypotheses.

## Project-specific package proposal
`src/qmg/research/india_monsoon_cpi_equity_surprise/`: `contracts.py`, `source_adapter.py`, `baseline.py`, `candidate.py`, `objective.py`, `evals.py`, `cli.py`, `tests/test_publication_clock.py`, `tests/test_negative_controls.py`.
Domain input: IMD daily district rain, crop sowing weights, RBI CPI release, state-level harvest, NSE sector returns. Main model: Hierarchical spatial distributed-lag regression + causal crop weighting. Optional next step: Weather-to-crop graph structural state-space model with uncertainty propagation.

## Interface safety
Keep public/paid/private adapters separate; no token strings, client data or scrape-prohibited market data in the repository. Export proposed schema examples with **synthetic rows only**. Runtime and tests are not implemented.
