# TOOLING — CFTC Positioning Concentration and Commodity Curve Convexity
**Implementation status:** PROPOSED — not present, installed, tested or version-pinned.

## Candidate research stack
`polars, statsmodels, arch (optional), cvxpy` plus Python 3.11+, pandas/Polars for typed time-vintage tables, NumPy/ SciPy for deterministic numeric checks, pytest for negative fixtures. Pin exact versions and solver backend during implementation.

## Shared reusable QMG components (future abstractions)
- `qmg_core.sources.vintages`: immutable record of source, first available time, revisions, license and redistribution rights.
- `qmg_core.data.contracts`: typed country/security/contract metadata, calendar alignment and unit coercion.
- `qmg_core.research.falsification`: pre-registered null/hypothesis and independent chronological or event-based holdout.
- `qmg_core.economics.execution`: bid/ask, financing, tax, funding, transaction costs, capacity and no-trade baselines.
- `qmg_core.optimization.feasibility`: domain-specific hard constraints and solver diagnostics.
- `qmg_core.reporting.evidence`: source citations, numerical check ledger, provenance and negative tests.

## Idea-specific module (future)
`src/qmg/research/cot_crowding_curve_convexity/`:
- `contracts.py` → CFTC contract market × Tuesday reference position × Friday public release, then weekly trade clock; check earliest action is CFTC publication/next executable session; no use of Tuesday positions on Tuesday.
- `sources.py` → primary data: CFTC Disaggregated COT futures positions, futures contracts prices/rolls, EIA physical inventories where applicable..
- `baseline.py` → Futures curve carry/roll-yield and 12-month time-series momentum..
- `candidate.py` → Positioning-conditioned conditional expected shortfall regression..
- `economics.py` → Enforce futures open interest participation cap, roll liquidity and margin stress; no physical commodity positions..
- `evals.py` → tail loss reduction, annualized Sharpe after roll/slippage, opportunity-cost drag and hedge stability.; stress CFTC taxonomy changes, combined report double-counting and slow publication may annihilate predictive edge..
- `cli.py` → fixture-only and authorized data runs.

## Data adapter classes
Public official URLs may be explored in a synthetic/open-data mode. Licensed data require a separately approved adapter. Restricted records are never stored in this public repo. No cross-tenant or credential sharing; no silent substitution of hypothetical prices for executable data.

## Reuse boundary
Point-in-time/vintage, claim verification, cost and benchmark utilities are shared. Domain-specific asset/country constraints must remain inside this idea module. Add audit tests before any runtime is considered available.
