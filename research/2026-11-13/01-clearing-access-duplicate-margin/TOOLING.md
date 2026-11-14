# TOOLING — Treasury Clearing Access-Path & Duplicate-Margin Optimizer
**Implementation status:** PROPOSED — not present, installed, tested or version-pinned.

## Candidate research stack
`cvxpy, OR-Tools, scipy, pydantic; synthetic FICC-like margin stress fixture` plus Python 3.11+, pandas/Polars for typed time-vintage tables, NumPy/ SciPy for deterministic numeric checks, pytest for negative fixtures. Pin exact versions and solver backend during implementation.

## Shared reusable QMG components (future abstractions)
- `qmg_core.sources.vintages`: immutable record of source, first available time, revisions, license and redistribution rights.
- `qmg_core.data.contracts`: typed country/security/contract metadata, calendar alignment and unit coercion.
- `qmg_core.research.falsification`: pre-registered null/hypothesis and independent chronological or event-based holdout.
- `qmg_core.economics.execution`: bid/ask, financing, tax, funding, transaction costs, capacity and no-trade baselines.
- `qmg_core.optimization.feasibility`: domain-specific hard constraints and solver diagnostics.
- `qmg_core.reporting.evidence`: source citations, numerical check ledger, provenance and negative tests.

## Idea-specific module (future)
`src/qmg/research/clearing_access_duplicate_margin/`:
- `contracts.py` → trade × eligible clearing access path × decision timestamp; check trade routing decision at quote acceptance; historical public aggregates are lagged and cannot be used as intraday quotes.
- `sources.py` → primary data: Eligible trade templates; path availability; historical quote spreads; initial/variation margin stress; capital/CCLF allocation; modeled netting sets; direct/sponsored/agent fees..
- `baseline.py` → Minimize executable repo rate ignoring path-specific costs, after validating that every route is eligible..
- `candidate.py` → Mixed-integer convex routing with separate margin, settlement and liquidity shadow prices..
- `economics.py` → Constrained by FICC participant access, available repo quote depth, account/entity eligibility and netting-set segregation..
- `evals.py` → USD all-in funding cost, dollar liquidity encumbrance, margin stress p99, ineligible route count, rejection rate.; stress Clearing rule exemptions and netting eligibility vary; estimated margin offsets could be nonportable across entities..
- `cli.py` → fixture-only and authorized data runs.

## Data adapter classes
Public official URLs may be explored in a synthetic/open-data mode. Licensed data require a separately approved adapter. Restricted records are never stored in this public repo. No cross-tenant or credential sharing; no silent substitution of hypothetical prices for executable data.

## Reuse boundary
Point-in-time/vintage, claim verification, cost and benchmark utilities are shared. Domain-specific asset/country constraints must remain inside this idea module. Add audit tests before any runtime is considered available.
