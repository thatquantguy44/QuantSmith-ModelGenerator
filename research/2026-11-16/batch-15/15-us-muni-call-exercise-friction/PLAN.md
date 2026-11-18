# Implementation plan — US Municipal Call-Exercise Friction Surface

**Scope:** United States tax-exempt callable municipal bonds. No modules described here currently exist in this batch.

## Data contract and architecture

Propose `adapters/muni_call_disclosures.py` => immutable raw manifest => `point_in_time/asof.py` => `us_muni_call_exercise_friction/features.py` => `baseline.py` / `candidate.py` => `evaluation.py` => review artifact. Native grain is **bond x call opportunity x public notice/financial filing event**. Required domain fields: EMMA official statements and public call notices, contemporaneously released issuer financials, trades with dissemination timestamps, call schedules, accrued interest and matched yield curves. Public browsing is not assumed licensed bulk extraction.

The common event envelope is `(entity_id, source_id, source_version, observed_at, published_at, received_at, available_at, effective_at, unit, currency, rights_class, payload_hash)`. Historical receive times may be unknown: record assumed latency and its provenance separately, never present it as an observed receipt. As-of joins select the most recent version actually available at the decision instant, retaining prior versions and amendments.

## Domain transformation and decision clock

Build refunding incentive, notice state, issuer friction and time-to-call. Target: call timing distribution, cash-flow forecast error and duration-adjusted bond return. Use only disclosures disseminated by prior close; trade at next obtainable firm offer/bid with a one-session latency. A call notice must enter at publication, not retroactively at the optional call date. Keep pending announcements distinct from legally effective constraints. Do not train on a later correction, a future completion/outcome or a delisted-only survivor universe.

## Model alternatives

Start with Exercise at first call date when modeled refunding savings exceed a fixed 3% threshold; compare yield-to-worst selection. Then implement Discrete-time survival model with economic refunding covariates. The expensive alternative is Hierarchical issuer stopping model with financing frictions and cash-flow scenario valuation; it is eligible only after a positive baseline-to-candidate comparison and a sufficient sample. Prefer the baseline if the advanced method's additional complexity does not clear net economic gates.

## Reviewable outputs and fallback

Return call probability surface, cash-flow distribution and duration-matched selection report. Save input manifest, time-mask violations, fit window, chosen parameters, cost scenario and reason for every excluded row. Every parsed call term needs a document page/span; conflicting extraordinary versus optional redemption clauses block valuation. Exceptions return HOLD/BLOCKED and preserve the original decision/book. No adapter may send orders, change contractual prices or upload private records.

## Dependencies and boundaries

MSRB bulk subscription, bond terms/identifier rights and executable dealer quote history as required. Optional authorized execution quotes and investor constraint profiles; absent. Public feasibility comes first; an absent private adapter is an explicit production blocker, not a justification to synthesize a historical result. Capacity review: Illustrative $40m matched-bond sleeve; cap issue ownership and trade size relative to observed turnover, allow days to execute and charge dealer markup. No presumption of instantaneous municipal execution. Shared libraries are specified in [TOOLING](TOOLING.md), tests in [EVALS](EVALS.md).
