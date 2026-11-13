# TOOLING — Manufactured-Dividend and Corporate-Action Loan Economics
**Implementation status:** PROPOSED — not present, installed, tested or version-pinned.

## Candidate research stack
`pandas, pydantic, OR-Tools, pytest; event calendar rule engine` plus Python 3.11+, pandas/Polars for typed time-vintage tables, NumPy/ SciPy for deterministic numeric checks, pytest for negative fixtures. Pin exact versions and solver backend during implementation.

## Shared reusable QMG components (future abstractions)
- `qmg_core.sources.vintages`: immutable record of source, first available time, revisions, license and redistribution rights.
- `qmg_core.data.contracts`: typed country/security/contract metadata, calendar alignment and unit coercion.
- `qmg_core.research.falsification`: pre-registered null/hypothesis and independent chronological or event-based holdout.
- `qmg_core.economics.execution`: bid/ask, financing, tax, funding, transaction costs, capacity and no-trade baselines.
- `qmg_core.optimization.feasibility`: domain-specific hard constraints and solver diagnostics.
- `qmg_core.reporting.evidence`: source citations, numerical check ledger, provenance and negative tests.

## Idea-specific module (future)
`src/qmg/research/manufactured_dividend_corporate_actions/`:
- `contracts.py` → security × beneficial owner program × corporate-action event × decision timestamp; check event decisions before ex-date cutoff, using only announced corporate actions and approved tax interpretations then available.
- `sources.py` → primary data: Ex/record/pay dates; loan life; fee accrual; event elections; dividend amounts; owner tax flags and permitted return/recall rules..
- `baseline.py` → Renew if lending fee remains positive and return only upon explicit mandatory recall..
- `candidate.py` → Rule-checked event economics and constrained loan life-cycle integer optimizer..
- `economics.py` → Only owner-permitted loans and action windows; supply cannot be fabricated by the optimizer..
- `evals.py` → net program income, missed payment events, operational exceptions, unauthorized action count.; stress Tax withholding, treaty benefits and manufactured-dividend treatment cannot be assumed from issuer-country information alone..
- `cli.py` → fixture-only and authorized data runs.

## Data adapter classes
Public official URLs may be explored in a synthetic/open-data mode. Licensed data require a separately approved adapter. Restricted records are never stored in this public repo. No cross-tenant or credential sharing; no silent substitution of hypothetical prices for executable data.

## Reuse boundary
Point-in-time/vintage, claim verification, cost and benchmark utilities are shared. Domain-specific asset/country constraints must remain inside this idea module. Add audit tests before any runtime is considered available.
