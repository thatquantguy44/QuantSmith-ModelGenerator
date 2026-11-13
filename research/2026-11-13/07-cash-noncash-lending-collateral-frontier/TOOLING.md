# TOOLING — Cash versus Noncash Loan-Collateral Economic Frontier
**Implementation status:** PROPOSED — not present, installed, tested or version-pinned.

## Candidate research stack
`cvxpy, scipy, pydantic, pandas; collateral convention normalizer` plus Python 3.11+, pandas/Polars for typed time-vintage tables, NumPy/ SciPy for deterministic numeric checks, pytest for negative fixtures. Pin exact versions and solver backend during implementation.

## Shared reusable QMG components (future abstractions)
- `qmg_core.sources.vintages`: immutable record of source, first available time, revisions, license and redistribution rights.
- `qmg_core.data.contracts`: typed country/security/contract metadata, calendar alignment and unit coercion.
- `qmg_core.research.falsification`: pre-registered null/hypothesis and independent chronological or event-based holdout.
- `qmg_core.economics.execution`: bid/ask, financing, tax, funding, transaction costs, capacity and no-trade baselines.
- `qmg_core.optimization.feasibility`: domain-specific hard constraints and solver diagnostics.
- `qmg_core.reporting.evidence`: source citations, numerical check ledger, provenance and negative tests.

## Idea-specific module (future)
`src/qmg/research/cash_noncash_lending_collateral_frontier/`:
- `contracts.py` → loan offer × collateral type × owner mandate × quotation timestamp; check quote acceptance before loan opening with known collateral terms, not end-of-day realized earnings.
- `sources.py` → primary data: Cash and noncash terms, rebate schedules, reinvestment constraints, asset eligibility, mark-to-market, haircuts and legal restrictions..
- `baseline.py` → Choose the highest headline loan spread among eligible offers..
- `candidate.py` → Loan-specific all-in economic break-even and constraints solver..
- `economics.py` → Constrained by approved collateral classes, reinvestment capacity, borrower credit and liquidity..
- `evals.py` → net economic revenue, risk capital per dollar, haircuts and eligibility breaches, retained lending volume.; stress Comparing unavailable cash reinvestment yield to executable noncash economics creates phantom spread..
- `cli.py` → fixture-only and authorized data runs.

## Data adapter classes
Public official URLs may be explored in a synthetic/open-data mode. Licensed data require a separately approved adapter. Restricted records are never stored in this public repo. No cross-tenant or credential sharing; no silent substitution of hypothetical prices for executable data.

## Reuse boundary
Point-in-time/vintage, claim verification, cost and benchmark utilities are shared. Domain-specific asset/country constraints must remain inside this idea module. Add audit tests before any runtime is considered available.
