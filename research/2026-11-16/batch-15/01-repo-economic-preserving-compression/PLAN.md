# Implementation plan — Repo Compression with Cash-Flow Preservation

**Scope:** US Treasury repo; one legal netting set at a time. No modules described here currently exist in this batch.

## Data contract and architecture

Propose `adapters/repo_ledger.py` => immutable raw manifest => `point_in_time/asof.py` => `repo_economic_preserving_compression/features.py` => `baseline.py` / `candidate.py` => `evaluation.py` => review artifact. Native grain is **repo ticket and dated cash/security obligation**. Required domain fields: Ticket ID, legal-set ID, participant pseudonym, CUSIP, start/end timestamps, cash principal, accrued interest, rate convention, face amount, consent flag and minimum lot. Public rules plus synthetic networks first; public aggregates cannot reconstruct a private trade graph.

The common event envelope is `(entity_id, source_id, source_version, observed_at, published_at, received_at, available_at, effective_at, unit, currency, rights_class, payload_hash)`. Historical receive times may be unknown: record assumed latency and its provenance separately, never present it as an observed receipt. As-of joins select the most recent version actually available at the decision instant, retaining prior versions and amendments.

## Domain transformation and decision clock

Build dated incidence matrices, lot constraints and consent mask. Target: retained gross notional and verified per-date cash/security conservation. Freeze the ledger at 14:00 America/New_York; use only confirmed records ingested by 13:55 and decisions before the relevant service cutoff. Cash-flow amendments received later enter the next solve. Keep pending announcements distinct from legally effective constraints. Do not train on a later correction, a future completion/outcome or a delisted-only survivor universe.

## Model alternatives

Start with Cancel exact opposite tickets bilaterally within a legal set; otherwise hold the original book. Then implement Mixed-integer minimum-cost circulation with exact cash-flow conservation. The expensive alternative is Robust multi-period compression with consent uncertainty and settlement-feasibility cuts; it is eligible only after a positive baseline-to-candidate comparison and a sufficient sample. Prefer the baseline if the advanced method's additional complexity does not clear net economic gates.

## Reviewable outputs and fallback

Return proposed tear-up/resizing schedule, exact flow certificate and rejected-action reasons. Save input manifest, time-mask violations, fit window, chosen parameters, cost scenario and reason for every excluded row. For a proposed 5,000-ticket set, target p95 solve time <=60 seconds and exact conservation certificate; infeasible or timed-out solves return original book. Exceptions return HOLD/BLOCKED and preserve the original decision/book. No adapter may send orders, change contractual prices or upload private records.

## Dependencies and boundaries

Licensed trade-processing/reference-data tools only if public rules and synthetic fixtures are insufficient; legal and consent records remain permissioned. Authorized repo ledger and legal-set approvals in a private deployment; none obtained or committed. Public feasibility comes first; an absent private adapter is an explicit production blocker, not a justification to synthesize a historical result. Capacity review: Illustrative $1bn eligible matched book; no directional risk capital assumed. Economics come from fewer messages and approved gross-capacity charges, not treating all removed notional as regulatory capital relief. Shared libraries are specified in [TOOLING](TOOLING.md), tests in [EVALS](EVALS.md).
