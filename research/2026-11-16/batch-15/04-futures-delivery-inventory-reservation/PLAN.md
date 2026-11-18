# Implementation plan — Treasury Futures Delivery Inventory Reservation

**Scope:** United States; Treasury futures deliverable baskets and securities loans. No modules described here currently exist in this batch.

## Data contract and architecture

Propose `adapters/treasury_delivery.py` => immutable raw manifest => `point_in_time/asof.py` => `futures_delivery_inventory_reservation/features.py` => `baseline.py` / `candidate.py` => `evaluation.py` => review artifact. Native grain is **CUSIP x futures contract x observation timestamp**. Required domain fields: Published conversion factors and contract rules; futures and cash bid/ask, repo fees, loan terms, delivery notices and hedge positions. Public basket tables are insufficient for option valuation.

The common event envelope is `(entity_id, source_id, source_version, observed_at, published_at, received_at, available_at, effective_at, unit, currency, rights_class, payload_hash)`. Historical receive times may be unknown: record assumed latency and its provenance separately, never present it as an observed receipt. As-of joins select the most recent version actually available at the decision instant, retaining prior versions and amendments.

## Domain transformation and decision clock

Build invoice value, basket eligibility and marginal delivery option shadow cost. Target: net lending revenue plus delivery economics for a fixed pre-existing futures obligation. Reserve at 15:00 America/Chicago using quotes available by 14:55 and current contract basket version; subsequent delivery notices are outcomes, never predictive features. Keep pending announcements distinct from legally effective constraints. Do not train on a later correction, a future completion/outcome or a delisted-only survivor universe.

## Model alternatives

Start with Hold back 10% of eligible basket inventory and allocate remaining loans using current fees. Then implement Scenario dynamic programming for marginal delivery-option value. The expensive alternative is Least-squares Monte Carlo with joint cash/futures/repo scenarios and integer delivery sizing; it is eligible only after a positive baseline-to-candidate comparison and a sufficient sample. Prefer the baseline if the advanced method's additional complexity does not clear net economic gates.

## Reviewable outputs and fallback

Return lendable face limits and delivery-feasibility certificate. Save input manifest, time-mask violations, fit window, chosen parameters, cost scenario and reason for every excluded row. Contract units, invoice rounding and delivery rules must be versioned and independently reconciled before optimization. Exceptions return HOLD/BLOCKED and preserve the original decision/book. No adapter may send orders, change contractual prices or upload private records.

## Dependencies and boundaries

Licensed synchronized cash Treasury, futures and security-specific financing prices. Existing futures obligations, inventory and loan restrictions; absent and excluded from public artifacts. Public feasibility comes first; an absent private adapter is an explicit production blocker, not a justification to synthesize a historical result. Capacity review: Illustrative $250m affected deliverable inventory. Limited by futures obligation size and deliverable-lot depth; do not take a new directional basis trade merely to generate lending revenue. Shared libraries are specified in [TOOLING](TOOLING.md), tests in [EVALS](EVALS.md).
