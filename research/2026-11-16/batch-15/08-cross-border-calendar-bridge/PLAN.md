# Implementation plan — Cross-Border Settlement Calendar Bridge Planner

**Scope:** US, euro area and UK financing settlement. No modules described here currently exist in this batch.

## Data contract and architecture

Propose `adapters/settlement_calendars.py` => immutable raw manifest => `point_in_time/asof.py` => `cross_border_calendar_bridge/features.py` => `baseline.py` / `candidate.py` => `evaluation.py` => review artifact. Native grain is **obligation leg x settlement service x UTC instant**. Required domain fields: Official service calendars and versioned cutoffs, announced closures/extensions, obligation currency/security legs and value dates, available prefunding routes and firm rates.

The common event envelope is `(entity_id, source_id, source_version, observed_at, published_at, received_at, available_at, effective_at, unit, currency, rights_class, payload_hash)`. Historical receive times may be unknown: record assumed latency and its provenance separately, never present it as an observed receipt. As-of joins select the most recent version actually available at the decision instant, retaining prior versions and amendments.

## Domain transformation and decision clock

Build service open intervals, version effective dates, cash-day gaps and DST conversion. Target: bridge cash-days and avoidable calendar exceptions. Plan at least two local business days before a known holiday, using rules announced by then. Unexpected outages are separate stress scenarios; announced future changes enter only after their publication. Keep pending announcements distinct from legally effective constraints. Do not train on a later correction, a future completion/outcome or a delisted-only survivor universe.

## Model alternatives

Start with Prefund every cross-border obligation two generic business days early, with manual holiday review. Then implement Time-expanded multi-service cash-flow network. The expensive alternative is Robust network flow with uncertain service extensions and intraday cash arrival bands; it is eligible only after a positive baseline-to-candidate comparison and a sufficient sample. Prefer the baseline if the advanced method's additional complexity does not clear net economic gates.

## Reviewable outputs and fallback

Return prefunding dates, minimal cash bridge and infeasible-leg alerts. Save input manifest, time-mask violations, fit window, chosen parameters, cost scenario and reason for every excluded row. Timezone-aware UTC storage with local service timezone preserved; unknown calendar version returns BLOCKED, never a guessed weekday. Exceptions return HOLD/BLOCKED and preserve the original decision/book. No adapter may send orders, change contractual prices or upload private records.

## Dependencies and boundaries

Licensed settlement-calendar/corporate-action reference feed if official histories are incomplete. Approved obligations, service memberships and bridge-funding limits; absent. Public feasibility comes first; an absent private adapter is an explicit production blocker, not a justification to synthesize a historical result. Capacity review: Illustrative $200m annual recurring bridge balances in USD equivalent; same approved obligations, no new FX carry position. Saving bounded by actual overlap days and bridge rates. Shared libraries are specified in [TOOLING](TOOLING.md), tests in [EVALS](EVALS.md).
