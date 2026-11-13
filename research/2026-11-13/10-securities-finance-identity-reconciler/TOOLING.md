# TOOLING — Cross-Book Securities Finance Identity Reconciliation Graph
**Implementation status:** PROPOSED — not present, installed, tested or version-pinned.

## Candidate research stack
`rapidfuzz, networkx, scipy.optimize, pydantic, duckdb` plus Python 3.11+, pandas/Polars for typed time-vintage tables, NumPy/ SciPy for deterministic numeric checks, pytest for negative fixtures. Pin exact versions and solver backend during implementation.

## Shared reusable QMG components (future abstractions)
- `qmg_core.sources.vintages`: immutable record of source, first available time, revisions, license and redistribution rights.
- `qmg_core.data.contracts`: typed country/security/contract metadata, calendar alignment and unit coercion.
- `qmg_core.research.falsification`: pre-registered null/hypothesis and independent chronological or event-based holdout.
- `qmg_core.economics.execution`: bid/ask, financing, tax, funding, transaction costs, capacity and no-trade baselines.
- `qmg_core.optimization.feasibility`: domain-specific hard constraints and solver diagnostics.
- `qmg_core.reporting.evidence`: source citations, numerical check ledger, provenance and negative tests.

## Idea-specific module (future)
`src/qmg/research/securities_finance_identity_reconciler/`:
- `contracts.py` → source record × canonical candidate × event version × timestamp; check real-time/overnight reconciliation; no future correction can be applied retroactively to a prior risk snapshot.
- `sources.py` → primary data: Synthetic records containing lifecycle events, ISIN/CUSIP, product type, settlement date, amount, counterparty alias and amendment chain..
- `baseline.py` → Exact ID join plus manually triaged fuzzy-name matches..
- `candidate.py` → Bipartite deterministic matching with hard identity constraints and provenance..
- `economics.py` → No market capacity required; scalability measured in records/day and audit/log cost, not claimed P&L..
- `evals.py` → false merge rate, unmatched %, time to resolve, duplicate exposure USD, manual review hours.; stress LLM or probabilistic model can silently merge legally distinct entities or settlement legs..
- `cli.py` → fixture-only and authorized data runs.

## Data adapter classes
Public official URLs may be explored in a synthetic/open-data mode. Licensed data require a separately approved adapter. Restricted records are never stored in this public repo. No cross-tenant or credential sharing; no silent substitution of hypothetical prices for executable data.

## Reuse boundary
Point-in-time/vintage, claim verification, cost and benchmark utilities are shared. Domain-specific asset/country constraints must remain inside this idea module. Add audit tests before any runtime is considered available.
