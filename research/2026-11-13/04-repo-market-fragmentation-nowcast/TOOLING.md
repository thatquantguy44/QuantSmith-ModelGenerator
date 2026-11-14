# TOOLING — Cleared Versus Tri-Party Repo Fragmentation Nowcast
**Implementation status:** PROPOSED — not present, installed, tested or version-pinned.

## Candidate research stack
`polars, statsmodels, ruptures, scikit-learn; revision-aware OFR adapter` plus Python 3.11+, pandas/Polars for typed time-vintage tables, NumPy/ SciPy for deterministic numeric checks, pytest for negative fixtures. Pin exact versions and solver backend during implementation.

## Shared reusable QMG components (future abstractions)
- `qmg_core.sources.vintages`: immutable record of source, first available time, revisions, license and redistribution rights.
- `qmg_core.data.contracts`: typed country/security/contract metadata, calendar alignment and unit coercion.
- `qmg_core.research.falsification`: pre-registered null/hypothesis and independent chronological or event-based holdout.
- `qmg_core.economics.execution`: bid/ask, financing, tax, funding, transaction costs, capacity and no-trade baselines.
- `qmg_core.optimization.feasibility`: domain-specific hard constraints and solver diagnostics.
- `qmg_core.reporting.evidence`: source citations, numerical check ledger, provenance and negative tests.

## Idea-specific module (future)
`src/qmg/research/repo_market_fragmentation_nowcast/`:
- `contracts.py` → venue × collateral class × tenor × underlying observation date, plus public publication timestamp; check risk update only after OFR release; cleared repo T+1 and tri-party T+2 availability; never use same-day unpublished values.
- `sources.py` → primary data: OFR cleared and tri-party rate-volume series; collateral categories; SOFR; weekly dealer aggregate financing; release metadata..
- `baseline.py` → SOFR level change and aggregate funding volume z-score..
- `candidate.py` → State-space latent fragmentation index with lag-aware missingness..
- `economics.py` → An alert/risk-overlay product first; any later trade signal faces venue access, funding tenor and prices..
- `evals.py` → next-session stress AUPRC, calibrated Brier score, false alarm rate, funding stress drawdown.; stress Revised/missing suppressed OFR cells and cross-venue holiday timing can create lookahead and artificial divergences..
- `cli.py` → fixture-only and authorized data runs.

## Data adapter classes
Public official URLs may be explored in a synthetic/open-data mode. Licensed data require a separately approved adapter. Restricted records are never stored in this public repo. No cross-tenant or credential sharing; no silent substitution of hypothetical prices for executable data.

## Reuse boundary
Point-in-time/vintage, claim verification, cost and benchmark utilities are shared. Domain-specific asset/country constraints must remain inside this idea module. Add audit tests before any runtime is considered available.
