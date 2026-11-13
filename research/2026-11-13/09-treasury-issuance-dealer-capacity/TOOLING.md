# TOOLING — Treasury Issuance-to-Dealer Intermediation Capacity Map
**Implementation status:** PROPOSED — not present, installed, tested or version-pinned.

## Candidate research stack
`statsmodels, pandas, ruptures, scipy; calendar vintage join engine` plus Python 3.11+, pandas/Polars for typed time-vintage tables, NumPy/ SciPy for deterministic numeric checks, pytest for negative fixtures. Pin exact versions and solver backend during implementation.

## Shared reusable QMG components (future abstractions)
- `qmg_core.sources.vintages`: immutable record of source, first available time, revisions, license and redistribution rights.
- `qmg_core.data.contracts`: typed country/security/contract metadata, calendar alignment and unit coercion.
- `qmg_core.research.falsification`: pre-registered null/hypothesis and independent chronological or event-based holdout.
- `qmg_core.economics.execution`: bid/ask, financing, tax, funding, transaction costs, capacity and no-trade baselines.
- `qmg_core.optimization.feasibility`: domain-specific hard constraints and solver diagnostics.
- `qmg_core.reporting.evidence`: source citations, numerical check ledger, provenance and negative tests.

## Idea-specific module (future)
`src/qmg/research/treasury_issuance_dealer_capacity/`:
- `contracts.py` → issuance cohort × week of publicly released dealer aggregates; check weekly close after primary dealer publication; never treat reported prior-week positions as contemporaneous.
- `sources.py` → primary data: Treasury auction issuance and settlement schedule; weekly primary dealer net positions/financing; OFR repo aggregates; public Treasury yield changes..
- `baseline.py` → Treasury yield volatility and calendar week indicators..
- `candidate.py` → Event-study + state-space dealer supply absorption proxy..
- `economics.py` → Public signal is a risk overlay; tradability needs actual Treasury order book, bid/ask, duration and repo access..
- `evals.py` → stress forecast Brier, AUPRC, lead-time, false positives and hedge drawdown.; stress Aggregate dealer reports cannot identify securities or dealers and issuance is endogenous to financing conditions..
- `cli.py` → fixture-only and authorized data runs.

## Data adapter classes
Public official URLs may be explored in a synthetic/open-data mode. Licensed data require a separately approved adapter. Restricted records are never stored in this public repo. No cross-tenant or credential sharing; no silent substitution of hypothetical prices for executable data.

## Reuse boundary
Point-in-time/vintage, claim verification, cost and benchmark utilities are shared. Domain-specific asset/country constraints must remain inside this idea module. Add audit tests before any runtime is considered available.
