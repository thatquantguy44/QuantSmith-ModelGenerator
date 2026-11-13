# TOOLING — US–Euro Sovereign Curve Shock Decomposition with Data Vintages
**Implementation status:** PROPOSED — not present, installed, tested or version-pinned.

## Candidate research stack
`statsmodels, scikit-learn, numpy, cvxpy` plus Python 3.11+, pandas/Polars for typed time-vintage tables, NumPy/ SciPy for deterministic numeric checks, pytest for negative fixtures. Pin exact versions and solver backend during implementation.

## Shared reusable QMG components (future abstractions)
- `qmg_core.sources.vintages`: immutable record of source, first available time, revisions, license and redistribution rights.
- `qmg_core.data.contracts`: typed country/security/contract metadata, calendar alignment and unit coercion.
- `qmg_core.research.falsification`: pre-registered null/hypothesis and independent chronological or event-based holdout.
- `qmg_core.economics.execution`: bid/ask, financing, tax, funding, transaction costs, capacity and no-trade baselines.
- `qmg_core.optimization.feasibility`: domain-specific hard constraints and solver diagnostics.
- `qmg_core.reporting.evidence`: source citations, numerical check ledger, provenance and negative tests.

## Idea-specific module (future)
`src/qmg/research/us_euro_curve_release_shocks/`:
- `contracts.py` → economic release event × curve tenor × publication instant × geography; check end-of-release or next-session decision after releases disseminate; avoid falsely assuming instant access to revised series.
- `sources.py` → primary data: ECB published euro yield curve, US yields and ALFRED macro vintages, official release times, FX hedges, rates futures cost..
- `baseline.py` → 60-day rolling DV01-neutral cross-market beta hedge..
- `candidate.py` → Vintaged announcement factor model plus shrinkage hedge weights..
- `economics.py` → Restrict first pass to liquid Treasury/Bund futures and realistic FX basis and futures trading costs..
- `evals.py` → OOS hedging variance reduction, implementation shortfall, tail DV01 loss, signal turnover.; stress Public releases cannot recreate market consensus surprises without a licensed historical consensus dataset or explicit no-consensus baseline..
- `cli.py` → fixture-only and authorized data runs.

## Data adapter classes
Public official URLs may be explored in a synthetic/open-data mode. Licensed data require a separately approved adapter. Restricted records are never stored in this public repo. No cross-tenant or credential sharing; no silent substitution of hypothetical prices for executable data.

## Reuse boundary
Point-in-time/vintage, claim verification, cost and benchmark utilities are shared. Domain-specific asset/country constraints must remain inside this idea module. Add audit tests before any runtime is considered available.
