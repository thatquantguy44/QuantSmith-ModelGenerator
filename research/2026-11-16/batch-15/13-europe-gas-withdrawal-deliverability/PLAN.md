# Implementation plan — European Gas Storage Deliverability Hedge

**Scope:** Germany, Netherlands, Italy and European gas hubs. No modules described here currently exist in this batch.

## Data contract and architecture

Propose `adapters/europe_gas_storage.py` => immutable raw manifest => `point_in_time/asof.py` => `europe_gas_withdrawal_deliverability/features.py` => `baseline.py` / `candidate.py` => `evaluation.py` => review artifact. Native grain is **storage facility x gas day x publication version**. Required domain fields: GIE published facility stocks/capacities/data-quality flags, publication versions, hub connectivity and outage notices; inventory-dependent performance curves need validated operator data or explicitly bounded assumptions. Licensed day-ahead/futures curves for hedging.

The common event envelope is `(entity_id, source_id, source_version, observed_at, published_at, received_at, available_at, effective_at, unit, currency, rights_class, payload_hash)`. Historical receive times may be unknown: record assumed latency and its provenance separately, never present it as an observed receipt. As-of joins select the most recent version actually available at the decision instant, retaining prior versions and amendments.

## Domain transformation and decision clock

Build withdrawal headroom, gas-day inventory state and hub connectivity. Target: winter peak procurement tail cost and deliverable MWh shortfall. Recompute after first verified daily publication; execute next liquid hub session with at least one-day lag when historical publication time is unknown. Revised storage values never replace first-release features. Keep pending announcements distinct from legally effective constraints. Do not train on a later correction, a future completion/outcome or a delisted-only survivor universe.

## Model alternatives

Start with Hedge ratio proportional to national percent-full deficit relative to trailing seasonal average. Then implement Constrained physical storage network and linear hedge projection. The expensive alternative is Stochastic dynamic storage model with uncertain withdrawal curves and robust hub hedge allocation; it is eligible only after a positive baseline-to-candidate comparison and a sufficient sample. Prefer the baseline if the advanced method's additional complexity does not clear net economic gates.

## Reviewable outputs and fallback

Return deliverability risk index and constrained seasonal hedge weights. Save input manifest, time-mask violations, fit window, chosen parameters, cost scenario and reason for every excluded row. Use gas-day definitions and MWh conversion consistently; data-quality flags propagate to bounds instead of becoming zero inventory. Exceptions return HOLD/BLOCKED and preserve the original decision/book. No adapter may send orders, change contractual prices or upload private records.

## Dependencies and boundaries

Licensed European gas hub forward, spread and execution history; operator performance data if public curves are inadequate. Optional authorized procurement exposures and storage rights; absent. Public feasibility comes first; an absent private adapter is an explicit production blocker, not a justification to synthesize a historical result. Capacity review: Illustrative $30m annual hedge exposure; use <=1% lagged hub/spread volume and explicit spread liquidity. USD ROI translates net EUR procurement savings at hedged rates; no assumed storage ownership. Shared libraries are specified in [TOOLING](TOOLING.md), tests in [EVALS](EVALS.md).
