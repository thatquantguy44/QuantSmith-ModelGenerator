# TOOLING — AI Infrastructure Capex-to-Power-and-Export Supply Chain Factor
**Implementation status:** PROPOSED — not present, installed, tested or version-pinned.

## Candidate research stack
`sec-edgar client, polars, networkx, pymc, cvxpy` plus Python 3.11+, pandas/Polars for typed time-vintage tables, NumPy/ SciPy for deterministic numeric checks, pytest for negative fixtures. Pin exact versions and solver backend during implementation.

## Shared reusable QMG components (future abstractions)
- `qmg_core.sources.vintages`: immutable record of source, first available time, revisions, license and redistribution rights.
- `qmg_core.data.contracts`: typed country/security/contract metadata, calendar alignment and unit coercion.
- `qmg_core.research.falsification`: pre-registered null/hypothesis and independent chronological or event-based holdout.
- `qmg_core.economics.execution`: bid/ask, financing, tax, funding, transaction costs, capacity and no-trade baselines.
- `qmg_core.optimization.feasibility`: domain-specific hard constraints and solver diagnostics.
- `qmg_core.reporting.evidence`: source citations, numerical check ledger, provenance and negative tests.

## Idea-specific module (future)
`src/qmg/research/ai_capex_power_export_factor/`:
- `contracts.py` → public company disclosure × filing-time vintage × geography × monthly energy/trade release; check rebalance monthly after latest public filings, energy updates and international trade release.
- `sources.py` → primary data: SEC EDGAR filed capital expenditure and commitments, EIA power demand/generation, public utility service-area reports, UN Comtrade semiconductor/electrical equipment trade..
- `baseline.py` → Equal-weight US tech/utility/semiconductor thematic basket with broad market hedge..
- `candidate.py` → Supply-chain bottleneck score anchored in publicly observed physical constraints..
- `economics.py` → Cap exposure to liquid industry ETFs/stocks; forecast vintages and reasonable turnover restrictions..
- `evals.py` → sector-neutral residual return, realized earnings revision, stock/industry turnover and capacity sensitivity.; stress Disclosure boilerplate, future guidance and partial energy-grid footprint can generate strong hindsight mapping bias..
- `cli.py` → fixture-only and authorized data runs.

## Data adapter classes
Public official URLs may be explored in a synthetic/open-data mode. Licensed data require a separately approved adapter. Restricted records are never stored in this public repo. No cross-tenant or credential sharing; no silent substitution of hypothetical prices for executable data.

## Reuse boundary
Point-in-time/vintage, claim verification, cost and benchmark utilities are shared. Domain-specific asset/country constraints must remain inside this idea module. Add audit tests before any runtime is considered available.
