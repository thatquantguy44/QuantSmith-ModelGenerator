# Implementation plan — Securities-Loan Dust-Lot Consolidation

**Scope:** US and developed-market equity lending. No modules described here currently exist in this batch.

## Data contract and architecture

Propose `adapters/loan_lots.py` => immutable raw manifest => `point_in_time/asof.py` => `securities_loan_dust_lot_consolidation/features.py` => `baseline.py` / `candidate.py` => `evaluation.py` => review artifact. Native grain is **owner x borrower x security loan lot x service day**. Required domain fields: Synthetic owner/borrower inventories, approved minimum lots, source shares, per-ticket servicing fees, loan quantities, movement cost and owner allocation rules. No real owner or borrower data are committed.

The common event envelope is `(entity_id, source_id, source_version, observed_at, published_at, received_at, available_at, effective_at, unit, currency, rights_class, payload_hash)`. Historical receive times may be unknown: record assumed latency and its provenance separately, never present it as an observed receipt. As-of joins select the most recent version actually available at the decision instant, retaining prior versions and amendments.

## Domain transformation and decision clock

Build fixed servicing charge, permitted owner-lot map and movement-cost matrix. Target: active-ticket count and net servicing-adjusted margin. Solve after confirmed end-of-day books and before next-day instruction cutoff; only booked demand and valid consent known at solve time enter. Settled movements are later outcomes. Keep pending announcements distinct from legally effective constraints. Do not train on a later correction, a future completion/outcome or a delisted-only survivor universe.

## Model alternatives

Start with Pro-rata eligible allocation across owners, subject to existing concentration caps. Then implement Fixed-charge transportation MILP. The expensive alternative is Multi-period lot consolidation with persistence penalties and uncertain demand bands; it is eligible only after a positive baseline-to-candidate comparison and a sufficient sample. Prefer the baseline if the advanced method's additional complexity does not clear net economic gates.

## Reviewable outputs and fallback

Return consolidation suggestions with per-owner exposure/revenue reconciliation. Save input manifest, time-mask violations, fit window, chosen parameters, cost scenario and reason for every excluded row. Deterministic tie-breaking and original-book fallback on infeasibility; quantity and owner revenue reconcile exactly to declared permitted changes. Exceptions return HOLD/BLOCKED and preserve the original decision/book. No adapter may send orders, change contractual prices or upload private records.

## Dependencies and boundaries

Licensed processing tariff/reference data where needed; no price history required for initial synthetic optimization. Authorized ticket-cost and owner allocation permissions; absent. Public feasibility comes first; an absent private adapter is an explicit production blocker, not a justification to synthesize a historical result. Capacity review: Illustrative 50,000 serviced lots per year; no market ADV capacity claim. Benefits limited by actual removable lots and movement/consent cost, not gross notional. Shared libraries are specified in [TOOLING](TOOLING.md), tests in [EVALS](EVALS.md).
