# TOOLING — Cash-Collateral Reinvestment Liquidity Run-Off Controller
**Implementation status:** PROPOSED — not present, installed, tested or version-pinned.

## Candidate research stack
`scipy.optimize, cvxpy, lifelines, numpy; maturity-ladder stress simulator` plus Python 3.11+, pandas/Polars for typed time-vintage tables, NumPy/ SciPy for deterministic numeric checks, pytest for negative fixtures. Pin exact versions and solver backend during implementation.

## Shared reusable QMG components (future abstractions)
- `qmg_core.sources.vintages`: immutable record of source, first available time, revisions, license and redistribution rights.
- `qmg_core.data.contracts`: typed country/security/contract metadata, calendar alignment and unit coercion.
- `qmg_core.research.falsification`: pre-registered null/hypothesis and independent chronological or event-based holdout.
- `qmg_core.economics.execution`: bid/ask, financing, tax, funding, transaction costs, capacity and no-trade baselines.
- `qmg_core.optimization.feasibility`: domain-specific hard constraints and solver diagnostics.
- `qmg_core.reporting.evidence`: source citations, numerical check ledger, provenance and negative tests.

## Idea-specific module (future)
`src/qmg/research/cash_collateral_reinvestment_runoff/`:
- `contracts.py` → cash collateral program × reinvestment maturity bucket × business day; check end-of-day reinvestment decision with availability of prior published cash flow and eligible settlement windows.
- `sources.py` → primary data: Loan termination flows; collateral principal; reinvestment settlement and maturity ladders; redemption windows; eligible funds; short-term yields; stress scenarios..
- `baseline.py` → Static liquidity buffer plus duration/weighted average life constraints..
- `candidate.py` → Conditional run-off survival model combined with stochastic cash-flow gap optimizer..
- `economics.py` → Capital is constrained by contractual permissible instruments, concentration, tenor limits and financing market depth..
- `evals.py` → 99% liquidity shortfall, reinvestment net yield, liquidity carry, stressed liquidations, breach count.; stress Return flows may cluster under crises; survivorship of reinvestment balances causes understated withdrawals..
- `cli.py` → fixture-only and authorized data runs.

## Data adapter classes
Public official URLs may be explored in a synthetic/open-data mode. Licensed data require a separately approved adapter. Restricted records are never stored in this public repo. No cross-tenant or credential sharing; no silent substitution of hypothetical prices for executable data.

## Reuse boundary
Point-in-time/vintage, claim verification, cost and benchmark utilities are shared. Domain-specific asset/country constraints must remain inside this idea module. Add audit tests before any runtime is considered available.
