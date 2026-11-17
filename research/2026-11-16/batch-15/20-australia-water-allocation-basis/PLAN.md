# Implementation plan — Australian Water Allocation Shadow Price and Crop Basis

**Scope:** Murray-Darling Basin, Australia; water allocations and agricultural exposure. No modules described here currently exist in this batch.

## Data contract and architecture

Propose `adapters/australia_water_market.py` => immutable raw manifest => `point_in_time/asof.py` => `australia_water_allocation_basis/features.py` => `baseline.py` / `candidate.py` => `evaluation.py` => review artifact. Native grain is **water zone x allocation release x reported trade and crop season**. Required domain fields: BOM public allocation decisions and water trades, first-publication/registration timestamps, transfer-zone limits, crop budgets, planting calendars and regional prices; licensed crop futures/basis and official agronomic response data to be resolved.

The common event envelope is `(entity_id, source_id, source_version, observed_at, published_at, received_at, available_at, effective_at, unit, currency, rights_class, payload_hash)`. Historical receive times may be unknown: record assumed latency and its provenance separately, never present it as an observed receipt. As-of joins select the most recent version actually available at the decision instant, retaining prior versions and amendments.

## Domain transformation and decision clock

Build announced allocation innovation, transfer-zone shadow price and crop-water budget. Target: regional crop-margin forecast and hedge basis-adjusted downside loss. Update only after verified allocation announcement; water transaction price enters at public reporting time, not settlement/trade date. Trade a hedge no earlier than next liquid session; use seasons as independent split units. Keep pending announcements distinct from legally effective constraints. Do not train on a later correction, a future completion/outcome or a delisted-only survivor universe.

## Model alternatives

Start with Seasonal allocation-volume score with a fixed regional crop basket and constant futures hedge ratio. Then implement Constrained crop-water optimization with allocation-shock local projections. The expensive alternative is Stochastic water/crop dynamic program and robust partial hedge across transfer zones; it is eligible only after a positive baseline-to-candidate comparison and a sufficient sample. Prefer the baseline if the advanced method's additional complexity does not clear net economic gates.

## Reviewable outputs and fallback

Return crop-margin scenario, local water shadow price and hedge-basis feasibility verdict. Save input manifest, time-mask violations, fit window, chosen parameters, cost scenario and reason for every excluded row. Separate entitlement from allocation units and record ML, hectares and currency explicitly; unknown zone connectivity blocks cross-zone flow. Exceptions return HOLD/BLOCKED and preserve the original decision/book. No adapter may send orders, change contractual prices or upload private records.

## Dependencies and boundaries

Licensed regional agricultural spot/futures prices and water-market transaction history if public reporting is incomplete. Optional authorized grower exposure/rights, excluded from public work; not obtained. Public feasibility comes first; an absent private adapter is an explicit production blocker, not a justification to synthesize a historical result. Capacity review: Illustrative $15m agricultural exposure, small research capacity. Limit futures to <=1% lagged volume; water transactions require separate legal/access review and are not assumed executable by the researcher. Shared libraries are specified in [TOOLING](TOOLING.md), tests in [EVALS](EVALS.md).
