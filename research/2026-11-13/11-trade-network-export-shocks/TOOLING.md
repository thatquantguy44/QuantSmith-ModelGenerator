# TOOLING — Trade-Network Export-Shock Transmission to Equity Sectors
**Implementation status:** PROPOSED — not present, installed, tested or version-pinned.

## Candidate research stack
`polars, networkx, scikit-learn, econml (optional), cvxpy` plus Python 3.11+, pandas/Polars for typed time-vintage tables, NumPy/ SciPy for deterministic numeric checks, pytest for negative fixtures. Pin exact versions and solver backend during implementation.

## Shared reusable QMG components (future abstractions)
- `qmg_core.sources.vintages`: immutable record of source, first available time, revisions, license and redistribution rights.
- `qmg_core.data.contracts`: typed country/security/contract metadata, calendar alignment and unit coercion.
- `qmg_core.research.falsification`: pre-registered null/hypothesis and independent chronological or event-based holdout.
- `qmg_core.economics.execution`: bid/ask, financing, tax, funding, transaction costs, capacity and no-trade baselines.
- `qmg_core.optimization.feasibility`: domain-specific hard constraints and solver diagnostics.
- `qmg_core.reporting.evidence`: source citations, numerical check ledger, provenance and negative tests.

## Idea-specific module (future)
`src/qmg/research/trade_network_export_shocks/`:
- `contracts.py` → reporter × partner × HS code × reference month × publication/availability timestamp; check monthly after trade report publication and revision; NEVER trade at reference-month timestamp.
- `sources.py` → primary data: UN Comtrade reported and partner-reported trade by HS code/month; sector country revenue mix; FX; sector returns and macro controls..
- `baseline.py` → Equal-weight country sector allocation with FX and local industrial production controls..
- `candidate.py` → Sparse directed trade graph factor with event-lag-aware regressions..
- `economics.py` → ETFs and liquid futures only for first implementation; portfolio turnover caps and country exposure floors..
- `evals.py` → OOS sector information coefficient, dollar-neutral Sharpe, earnings revision hit rate, turnover and tail loss.; stress Revisions, late reporters, trade re-exports and mapping HS codes to listed firms can create survivorship and spurious exposure..
- `cli.py` → fixture-only and authorized data runs.

## Data adapter classes
Public official URLs may be explored in a synthetic/open-data mode. Licensed data require a separately approved adapter. Restricted records are never stored in this public repo. No cross-tenant or credential sharing; no silent substitution of hypothetical prices for executable data.

## Reuse boundary
Point-in-time/vintage, claim verification, cost and benchmark utilities are shared. Domain-specific asset/country constraints must remain inside this idea module. Add audit tests before any runtime is considered available.
