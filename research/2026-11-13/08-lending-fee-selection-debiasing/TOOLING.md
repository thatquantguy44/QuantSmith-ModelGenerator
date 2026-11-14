# TOOLING — Securities-Lending Fee Observability & Selection-Bias Corrector
**Implementation status:** PROPOSED — not present, installed, tested or version-pinned.

## Candidate research stack
`statsmodels, pymc, scikit-learn, polars; propensity-weighting and uncertainty library` plus Python 3.11+, pandas/Polars for typed time-vintage tables, NumPy/ SciPy for deterministic numeric checks, pytest for negative fixtures. Pin exact versions and solver backend during implementation.

## Shared reusable QMG components (future abstractions)
- `qmg_core.sources.vintages`: immutable record of source, first available time, revisions, license and redistribution rights.
- `qmg_core.data.contracts`: typed country/security/contract metadata, calendar alignment and unit coercion.
- `qmg_core.research.falsification`: pre-registered null/hypothesis and independent chronological or event-based holdout.
- `qmg_core.economics.execution`: bid/ask, financing, tax, funding, transaction costs, capacity and no-trade baselines.
- `qmg_core.optimization.feasibility`: domain-specific hard constraints and solver diagnostics.
- `qmg_core.reporting.evidence`: source citations, numerical check ledger, provenance and negative tests.

## Idea-specific module (future)
`src/qmg/research/lending_fee_selection_debiasing/`:
- `contracts.py` → security × lending day × vendor/contributor population; check benchmark at next published cutoff; never use end-of-day contributions before receipt.
- `sources.py` → primary data: Contributed executed fee samples; public security volume/short-interest proxies; locate response metadata; source coverage and revisions..
- `baseline.py` → Daily equally weighted or outstanding-value-weighted observed market fees..
- `candidate.py` → Doubly robust weighting with overlap and selection-sensitivity intervals..
- `economics.py` → Primarily an internal benchmark/data product; no automatic quoting when source coverage or liquidity is inadequate..
- `evals.py` → cross-contributor benchmark error, interval coverage, abstention, quote drift, market breadth coverage.; stress Missing-not-at-random selection cannot be identified from executed loans alone; confidence intervals can be falsely narrow..
- `cli.py` → fixture-only and authorized data runs.

## Data adapter classes
Public official URLs may be explored in a synthetic/open-data mode. Licensed data require a separately approved adapter. Restricted records are never stored in this public repo. No cross-tenant or credential sharing; no silent substitution of hypothetical prices for executable data.

## Reuse boundary
Point-in-time/vintage, claim verification, cost and benchmark utilities are shared. Domain-specific asset/country constraints must remain inside this idea module. Add audit tests before any runtime is considered available.
