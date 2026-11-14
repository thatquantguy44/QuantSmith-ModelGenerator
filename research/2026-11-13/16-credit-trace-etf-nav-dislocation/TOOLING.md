# TOOLING — Corporate-Bond TRACE Liquidity-to-ETF NAV Stress Transmission
**Implementation status:** PROPOSED — not present, installed, tested or version-pinned.

## Candidate research stack
`pandas, polars, scipy, statsmodels; bond-to-ETF mapping index` plus Python 3.11+, pandas/Polars for typed time-vintage tables, NumPy/ SciPy for deterministic numeric checks, pytest for negative fixtures. Pin exact versions and solver backend during implementation.

## Shared reusable QMG components (future abstractions)
- `qmg_core.sources.vintages`: immutable record of source, first available time, revisions, license and redistribution rights.
- `qmg_core.data.contracts`: typed country/security/contract metadata, calendar alignment and unit coercion.
- `qmg_core.research.falsification`: pre-registered null/hypothesis and independent chronological or event-based holdout.
- `qmg_core.economics.execution`: bid/ask, financing, tax, funding, transaction costs, capacity and no-trade baselines.
- `qmg_core.optimization.feasibility`: domain-specific hard constraints and solver diagnostics.
- `qmg_core.reporting.evidence`: source citations, numerical check ledger, provenance and negative tests.

## Idea-specific module (future)
`src/qmg/research/credit_trace_etf_nav_dislocation/`:
- `contracts.py` → bond × disseminated trade timestamp × ETF NAV publication timestamp; check end-of-session / next-session ETF risk adjustment only; public aggregate data may not cover security-level historical panel.
- `sources.py` → primary data: FINRA TRACE public aggregate/trade pages, subscription historical bond records, ETF market prices, NAV timestamps, bond indices, CDX basis..
- `baseline.py` → ETF realized volatility and quoted bid-ask spread..
- `candidate.py` → Robust bond-liquidity dispersion index and ETF tracking-state model..
- `economics.py` → Only liquid ETFs and hedges, no synthetic bond execution assuming NAV arbitrage..
- `evals.py` → tracking error forecast, credit tail loss, hedge slippage, redemption-state calibration.; stress Reported bond prices may be size-capped/delayed; TRACE trade access/licensing varies and NAV can embed stale marks..
- `cli.py` → fixture-only and authorized data runs.

## Data adapter classes
Public official URLs may be explored in a synthetic/open-data mode. Licensed data require a separately approved adapter. Restricted records are never stored in this public repo. No cross-tenant or credential sharing; no silent substitution of hypothetical prices for executable data.

## Reuse boundary
Point-in-time/vintage, claim verification, cost and benchmark utilities are shared. Domain-specific asset/country constraints must remain inside this idea module. Add audit tests before any runtime is considered available.
