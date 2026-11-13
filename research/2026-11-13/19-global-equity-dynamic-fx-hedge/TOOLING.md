# TOOLING — Dynamic Currency-Hedge and Rebalancing Tax for Global Equity
**Implementation status:** PROPOSED — not present, installed, tested or version-pinned.

## Candidate research stack
`cvxpy, scipy, pandas, riskfolio (optional)` plus Python 3.11+, pandas/Polars for typed time-vintage tables, NumPy/ SciPy for deterministic numeric checks, pytest for negative fixtures. Pin exact versions and solver backend during implementation.

## Shared reusable QMG components (future abstractions)
- `qmg_core.sources.vintages`: immutable record of source, first available time, revisions, license and redistribution rights.
- `qmg_core.data.contracts`: typed country/security/contract metadata, calendar alignment and unit coercion.
- `qmg_core.research.falsification`: pre-registered null/hypothesis and independent chronological or event-based holdout.
- `qmg_core.economics.execution`: bid/ask, financing, tax, funding, transaction costs, capacity and no-trade baselines.
- `qmg_core.optimization.feasibility`: domain-specific hard constraints and solver diagnostics.
- `qmg_core.reporting.evidence`: source citations, numerical check ledger, provenance and negative tests.

## Idea-specific module (future)
`src/qmg/research/global_equity_dynamic_fx_hedge/`:
- `contracts.py` → country equity market × FX forward tenor × monthly rebalance date; check rebalance at scheduled month-end using prior-close prices and then-available forward quotes.
- `sources.py` → primary data: Country index total returns, currency spot/forward curves, FX liquidity, investability restrictions and funding rates..
- `baseline.py` → 50% static currency hedges plus equal-risk country weights and quarterly turnover..
- `candidate.py` → Robust covariance and transaction-cost-aware FX hedge optimizer..
- `economics.py` → Limit to index futures/ETFs and deliverable/non-deliverable forward liquidity; enforce market access and capital controls..
- `evals.py` → after-cost drawdown, lower-tail CVaR, rolling correlation, FX hedge turnover and volatility.; stress Country index histories have vendor survivorship and free-float methodological changes; FX pricing may be unavailable at allocated size..
- `cli.py` → fixture-only and authorized data runs.

## Data adapter classes
Public official URLs may be explored in a synthetic/open-data mode. Licensed data require a separately approved adapter. Restricted records are never stored in this public repo. No cross-tenant or credential sharing; no silent substitution of hypothetical prices for executable data.

## Reuse boundary
Point-in-time/vintage, claim verification, cost and benchmark utilities are shared. Domain-specific asset/country constraints must remain inside this idea module. Add audit tests before any runtime is considered available.
