# TOOLING — Weather Forecast Revision as an Electricity-to-Gas Risk Hedge
**Implementation status:** PROPOSED — not present, installed, tested or version-pinned.

## Candidate research stack
`xarray, pandas, statsmodels, lightgbm (optional), cvxpy` plus Python 3.11+, pandas/Polars for typed time-vintage tables, NumPy/ SciPy for deterministic numeric checks, pytest for negative fixtures. Pin exact versions and solver backend during implementation.

## Shared reusable QMG components (future abstractions)
- `qmg_core.sources.vintages`: immutable record of source, first available time, revisions, license and redistribution rights.
- `qmg_core.data.contracts`: typed country/security/contract metadata, calendar alignment and unit coercion.
- `qmg_core.research.falsification`: pre-registered null/hypothesis and independent chronological or event-based holdout.
- `qmg_core.economics.execution`: bid/ask, financing, tax, funding, transaction costs, capacity and no-trade baselines.
- `qmg_core.optimization.feasibility`: domain-specific hard constraints and solver diagnostics.
- `qmg_core.reporting.evidence`: source citations, numerical check ledger, provenance and negative tests.

## Idea-specific module (future)
`src/qmg/research/weather_electricity_gas_forecast_revisions/`:
- `contracts.py` → balancing authority × weather forecast issuance × lead hour; check forecast issuance is the earliest legal decision; never consume later realized weather or EIA actual load before release.
- `sources.py` → primary data: NWS issued and archived forecasts, EIA balancing authority hourly load and generation, power/gas futures settlements and basis..
- `baseline.py` → Seasonal degree-day demand regression and absolute temperature forecasts..
- `candidate.py` → Net-load forecast-revision elasticity with non-linear stress threshold..
- `economics.py` → Trade via highly liquid gas futures or energy equity baskets, with geographic basis and sector beta mismatch priced..
- `evals.py` → load p95 quantile loss, probabilistic calibration, hedge tracking error, net futures carry.; stress Archive of *historical forecasts as issued* may be inaccessible; today's historical observations are not contemporaneous forecasts..
- `cli.py` → fixture-only and authorized data runs.

## Data adapter classes
Public official URLs may be explored in a synthetic/open-data mode. Licensed data require a separately approved adapter. Restricted records are never stored in this public repo. No cross-tenant or credential sharing; no silent substitution of hypothetical prices for executable data.

## Reuse boundary
Point-in-time/vintage, claim verification, cost and benchmark utilities are shared. Domain-specific asset/country constraints must remain inside this idea module. Add audit tests before any runtime is considered available.
