# TOOLING — Settlement-Fail Buy-In versus Wait Optimal Stopping
**Implementation status:** PROPOSED — not present, installed, tested or version-pinned.

## Candidate research stack
`scipy, lifelines, numpy, pydantic; finite-horizon stopping solver` plus Python 3.11+, pandas/Polars for typed time-vintage tables, NumPy/ SciPy for deterministic numeric checks, pytest for negative fixtures. Pin exact versions and solver backend during implementation.

## Shared reusable QMG components (future abstractions)
- `qmg_core.sources.vintages`: immutable record of source, first available time, revisions, license and redistribution rights.
- `qmg_core.data.contracts`: typed country/security/contract metadata, calendar alignment and unit coercion.
- `qmg_core.research.falsification`: pre-registered null/hypothesis and independent chronological or event-based holdout.
- `qmg_core.economics.execution`: bid/ask, financing, tax, funding, transaction costs, capacity and no-trade baselines.
- `qmg_core.optimization.feasibility`: domain-specific hard constraints and solver diagnostics.
- `qmg_core.reporting.evidence`: source citations, numerical check ledger, provenance and negative tests.

## Idea-specific module (future)
`src/qmg/research/fail_buyin_optimal_stopping/`:
- `contracts.py` → failed settlement instruction × elapsed failed day × cut-off timestamp; check business-day cure decisions only after confirmed fail and remedy eligibility.
- `sources.py` → primary data: Public dealer failure aggregates for calibration; synthetic failure life histories; approved buy-in quotes, fails charges and legal remedies..
- `baseline.py` → Auto-escalate after fixed N-day failure age..
- `candidate.py` → Discrete-time survival model with exact dynamic-programming stopping rule..
- `economics.py` → Limited by available deliverable security and realistic executable cover bids..
- `evals.py` → resolved failure days, total cure cost, forced buy-in count, missed deadline, tail loss.; stress Fails charges and rights to enforce buy-ins differ by asset, market and contract; wrong assumptions invalidate decisions..
- `cli.py` → fixture-only and authorized data runs.

## Data adapter classes
Public official URLs may be explored in a synthetic/open-data mode. Licensed data require a separately approved adapter. Restricted records are never stored in this public repo. No cross-tenant or credential sharing; no silent substitution of hypothetical prices for executable data.

## Reuse boundary
Point-in-time/vintage, claim verification, cost and benchmark utilities are shared. Domain-specific asset/country constraints must remain inside this idea module. Add audit tests before any runtime is considered available.
