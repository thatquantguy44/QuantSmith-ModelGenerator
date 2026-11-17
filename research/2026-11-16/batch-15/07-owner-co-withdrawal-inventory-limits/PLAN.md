# Implementation plan — Owner Co-Withdrawal Limits for Lendable Inventory

**Scope:** US and European agency lending mandates. No modules described here currently exist in this batch.

## Data contract and architecture

Propose `adapters/owner_inventory.py` => immutable raw manifest => `point_in_time/asof.py` => `owner_co_withdrawal_inventory_limits/features.py` => `baseline.py` / `candidate.py` => `evaluation.py` => review artifact. Native grain is **owner x security x dated available-inventory snapshot**. Required domain fields: Permissioned daily available/withdrawn quantities by owner and security, mandate inception/termination, owner-group lineage, public N-PORT filings and known rebalance calendars. Public monthly/quarterly holdings are lagged aggregate context only.

The common event envelope is `(entity_id, source_id, source_version, observed_at, published_at, received_at, available_at, effective_at, unit, currency, rights_class, payload_hash)`. Historical receive times may be unknown: record assumed latency and its provenance separately, never present it as an observed receipt. As-of joins select the most recent version actually available at the decision instant, retaining prior versions and amendments.

## Domain transformation and decision clock

Build common withdrawal factor, owner lineage groups and replacement tail scenarios. Target: joint inventory-shortfall distribution and net cost of an allocation limit. Set next-day inventory limits after local close using confirmed availability received by cutoff; public fund holdings enter at filing acceptance, not portfolio as-of date. Never condition on the owner's future sale or recall notice. Keep pending announcements distinct from legally effective constraints. Do not train on a later correction, a future completion/outcome or a delisted-only survivor universe.

## Model alternatives

Start with Static 10% owner concentration cap with independent withdrawal probabilities. Then implement Hierarchical common-factor withdrawal model and CVaR allocation. The expensive alternative is Distributionally robust copula stress allocation with mandate-group shocks; it is eligible only after a positive baseline-to-candidate comparison and a sufficient sample. Prefer the baseline if the advanced method's additional complexity does not clear net economic gates.

## Reviewable outputs and fallback

Return source concentration limits and joint-withdrawal stress certificate. Save input manifest, time-mask violations, fit window, chosen parameters, cost scenario and reason for every excluded row. No raw owner identity or positions in public artifacts; a private run must use pseudonymous IDs and lineage access controls. Exceptions return HOLD/BLOCKED and preserve the original decision/book. No adapter may send orders, change contractual prices or upload private records.

## Dependencies and boundaries

Licensed owner/fund classification and securities-lending price history, subject to rights. Owner-level availability and mandate lineage, with explicit consent and minimum-access controls; absent. Public feasibility comes first; an absent private adapter is an explicit production blocker, not a justification to synthesize a historical result. Capacity review: Illustrative $500m supported inventory; direct benefits limited to replacement-cost savings and retained fee revenue. Extreme withdrawals may have no feasible replacement regardless of model. Shared libraries are specified in [TOOLING](TOOLING.md), tests in [EVALS](EVALS.md).
