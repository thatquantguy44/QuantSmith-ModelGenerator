# TOOLING — Tri-Party Collateral Eligibility Clause-to-Constraint Compiler
**Implementation status:** PROPOSED — not present, installed, tested or version-pinned.

## Candidate research stack
`pydantic, lark, networkx, pytest; optional LLM extraction only as proposer` plus Python 3.11+, pandas/Polars for typed time-vintage tables, NumPy/ SciPy for deterministic numeric checks, pytest for negative fixtures. Pin exact versions and solver backend during implementation.

## Shared reusable QMG components (future abstractions)
- `qmg_core.sources.vintages`: immutable record of source, first available time, revisions, license and redistribution rights.
- `qmg_core.data.contracts`: typed country/security/contract metadata, calendar alignment and unit coercion.
- `qmg_core.research.falsification`: pre-registered null/hypothesis and independent chronological or event-based holdout.
- `qmg_core.economics.execution`: bid/ask, financing, tax, funding, transaction costs, capacity and no-trade baselines.
- `qmg_core.optimization.feasibility`: domain-specific hard constraints and solver diagnostics.
- `qmg_core.reporting.evidence`: source citations, numerical check ledger, provenance and negative tests.

## Idea-specific module (future)
`src/qmg/research/triparty_eligibility_compiler/`:
- `contracts.py` → contract clause × effective version × collateral asset × valuation time; check rules valid at collateral decision; amendments apply from legal effective date, not document creation date.
- `sources.py` → primary data: Synthetic collateral schedules; asset master; rating/issuer; eligibility categories; haircut tables; human-labeled clause examples..
- `baseline.py` → Rule tables hand-transcribed and checked by two human operators..
- `candidate.py` → Schema-constrained text extraction with symbolic eligibility evaluation and abstention..
- `economics.py` → Can serve as quality-gate software without trading access; execution requires approved legal rules and certified contracts..
- `evals.py` → false eligibility acceptance rate, false rejection rate, review labor, coverage, abstention, parse latency.; stress Natural-language ambiguity, contract precedence and jurisdiction-specific clauses make full automation unsafe..
- `cli.py` → fixture-only and authorized data runs.

## Data adapter classes
Public official URLs may be explored in a synthetic/open-data mode. Licensed data require a separately approved adapter. Restricted records are never stored in this public repo. No cross-tenant or credential sharing; no silent substitution of hypothetical prices for executable data.

## Reuse boundary
Point-in-time/vintage, claim verification, cost and benchmark utilities are shared. Domain-specific asset/country constraints must remain inside this idea module. Add audit tests before any runtime is considered available.
