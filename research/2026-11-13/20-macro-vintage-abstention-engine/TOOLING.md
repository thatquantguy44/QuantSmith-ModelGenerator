# TOOLING — Macro-Vintage Integrity Engine with Prediction Abstention
**Implementation status:** PROPOSED — not present, installed, tested or version-pinned.

## Candidate research stack
`polars, duckdb, pydantic, conformal-prediction package (optional), pytest` plus Python 3.11+, pandas/Polars for typed time-vintage tables, NumPy/ SciPy for deterministic numeric checks, pytest for negative fixtures. Pin exact versions and solver backend during implementation.

## Shared reusable QMG components (future abstractions)
- `qmg_core.sources.vintages`: immutable record of source, first available time, revisions, license and redistribution rights.
- `qmg_core.data.contracts`: typed country/security/contract metadata, calendar alignment and unit coercion.
- `qmg_core.research.falsification`: pre-registered null/hypothesis and independent chronological or event-based holdout.
- `qmg_core.economics.execution`: bid/ask, financing, tax, funding, transaction costs, capacity and no-trade baselines.
- `qmg_core.optimization.feasibility`: domain-specific hard constraints and solver diagnostics.
- `qmg_core.reporting.evidence`: source citations, numerical check ledger, provenance and negative tests.

## Idea-specific module (future)
`src/qmg/research/macro_vintage_abstention_engine/`:
- `contracts.py` → economic indicator × observation period × release date × vintage ID; check update only after first verified public release; revisions must enter as new events, not retroactively.
- `sources.py` → primary data: ALFRED historical revisions, ECB yield releases, OECD SDMX data vintage calendars, US/global market proxies..
- `baseline.py` → Always-on macro momentum score built from latest-vintage series..
- `candidate.py` → As-of macro feature store with release-confidence model and abstention..
- `economics.py` → Primarily a reusable research data-quality service; alpha/executable returns need licensed market backtest..
- `evals.py` → revision-induced backtest bias, selective risk loss, coverage, false alarm rate, time-to-data-availability.; stress ALFRED historical series coverage, future revisions and OECD methodological breaks can be incomplete; abstention selection bias..
- `cli.py` → fixture-only and authorized data runs.

## Data adapter classes
Public official URLs may be explored in a synthetic/open-data mode. Licensed data require a separately approved adapter. Restricted records are never stored in this public repo. No cross-tenant or credential sharing; no silent substitution of hypothetical prices for executable data.

## Reuse boundary
Point-in-time/vintage, claim verification, cost and benchmark utilities are shared. Domain-specific asset/country constraints must remain inside this idea module. Add audit tests before any runtime is considered available.
