# Implementation plan — India Bond Index-Flow Saturation

**Scope:** India government bonds; emerging-market capital flows. No modules described here currently exist in this batch.

## Data contract and architecture

Propose `adapters/india_index_events.py` => immutable raw manifest => `point_in_time/asof.py` => `india_index_flow_duration_neutral/features.py` => `baseline.py` / `candidate.py` => `evaluation.py` => review artifact. Native grain is **government bond x announcement/rebalance cohort x public flow release**. Required domain fields: RBI FAR/public market context, dated index-provider inclusion/weight notices, foreign ownership/flows, bond eligibility, free-float and issue cash flows; local executable price and hedge history.

The common event envelope is `(entity_id, source_id, source_version, observed_at, published_at, received_at, available_at, effective_at, unit, currency, rights_class, payload_hash)`. Historical receive times may be unknown: record assumed latency and its provenance separately, never present it as an observed receipt. As-of joins select the most recent version actually available at the decision instant, retaining prior versions and amendments.

## Domain transformation and decision clock

Build announced flow pressure, free-float turnover and lagged foreign ownership saturation. Target: 20-session inclusion-window residual return and diminishing impact at high ownership. Act next Mumbai session after a verified inclusion announcement or ownership release; close at a predeclared post-effective window. Never use final index weights or future ownership before announcement. Keep pending announcements distinct from legally effective constraints. Do not train on a later correction, a future completion/outcome or a delisted-only survivor universe.

## Model alternatives

Start with Equal-risk inclusion-event basket versus duration-matched eligible controls. Then implement Matched staggered event study with demand-pressure interactions. The expensive alternative is Doubly robust event design plus a structural price-impact saturation curve; it is eligible only after a positive baseline-to-candidate comparison and a sufficient sample. Prefer the baseline if the advanced method's additional complexity does not clear net economic gates.

## Reviewable outputs and fallback

Return event-study estimands, placebo diagnostics and duration-neutral research basket. Save input manifest, time-mask violations, fit window, chosen parameters, cost scenario and reason for every excluded row. Announced and effective membership must occupy separate columns; unknown original announcement time blocks that cohort. Exceptions return HOLD/BLOCKED and preserve the original decision/book. No adapter may send orders, change contractual prices or upload private records.

## Dependencies and boundaries

Licensed dated index membership/weights, local bond pricing and public-ownership data distribution rights. Optional authorized execution records and foreign-investor access approval; absent. Public feasibility comes first; an absent private adapter is an explicit production blocker, not a justification to synthesize a historical result. Capacity review: Illustrative $50m duration-neutral basket, capped at 1% issue turnover with market access and FX hedging charged. Passive flow estimates are not executable demand guarantees. Shared libraries are specified in [TOOLING](TOOLING.md), tests in [EVALS](EVALS.md).
