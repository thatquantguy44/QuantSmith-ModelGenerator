# TOOLING — Central-Bank Communication Semantic Surprise Across Languages
**Implementation status:** PROPOSED — not present, installed, tested or version-pinned.

## Candidate research stack
`sentence-transformers, pydantic, polars, sklearn, pytest; evidence span validator` plus Python 3.11+, pandas/Polars for typed time-vintage tables, NumPy/ SciPy for deterministic numeric checks, pytest for negative fixtures. Pin exact versions and solver backend during implementation.

## Shared reusable QMG components (future abstractions)
- `qmg_core.sources.vintages`: immutable record of source, first available time, revisions, license and redistribution rights.
- `qmg_core.data.contracts`: typed country/security/contract metadata, calendar alignment and unit coercion.
- `qmg_core.research.falsification`: pre-registered null/hypothesis and independent chronological or event-based holdout.
- `qmg_core.economics.execution`: bid/ask, financing, tax, funding, transaction costs, capacity and no-trade baselines.
- `qmg_core.optimization.feasibility`: domain-specific hard constraints and solver diagnostics.
- `qmg_core.reporting.evidence`: source citations, numerical check ledger, provenance and negative tests.

## Idea-specific module (future)
`src/qmg/research/central_bank_semantic_surprise/`:
- `contracts.py` → central-bank event × original language × statement version × publication timestamp; check after official statement becomes public; never permit news articles, transcripts or price reactions from after decision in input.
- `sources.py` → primary data: Versioned official policy statements; actual publication timestamps; pre-event interest rate futures; FX and rates price bars; translated text audit..
- `baseline.py` → Policy rate surprise (or no-surprise dummy without licensed expectation) and prior-day rate changes..
- `candidate.py` → Source-grounded claim-difference extractor with multilingual uncertainty and simple linear evaluation..
- `economics.py` → Only next-session liquid FX/rates futures; policy event size, slippage and gap risk explicitly costed..
- `evals.py` → out-of-sample price direction log loss, FX hedge information ratio, translation agreement and unsupported claim rate.; stress Translation distortions, backfilled statement updates, and post-event news leakage are especially severe for multilingual event models..
- `cli.py` → fixture-only and authorized data runs.

## Data adapter classes
Public official URLs may be explored in a synthetic/open-data mode. Licensed data require a separately approved adapter. Restricted records are never stored in this public repo. No cross-tenant or credential sharing; no silent substitution of hypothetical prices for executable data.

## Reuse boundary
Point-in-time/vintage, claim verification, cost and benchmark utilities are shared. Domain-specific asset/country constraints must remain inside this idea module. Add audit tests before any runtime is considered available.
