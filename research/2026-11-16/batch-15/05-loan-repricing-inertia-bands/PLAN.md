# Implementation plan — Stock-Loan Repricing Bands with Relationship Friction

**Scope:** United States and developed-Europe equity loans. No modules described here currently exist in this batch.

## Data contract and architecture

Propose `adapters/loan_repricing.py` => immutable raw manifest => `point_in_time/asof.py` => `loan_repricing_inertia_bands/features.py` => `baseline.py` / `candidate.py` => `evaluation.py` => review artifact. Native grain is **loan x repricing proposal/response event**. Required domain fields: Existing-loan fee changes, proposal/acknowledgment timestamps, rejected changes, borrower exits, balances, fee benchmarks and support-message labor. A contributed fee panel alone cannot identify retention elasticity.

The common event envelope is `(entity_id, source_id, source_version, observed_at, published_at, received_at, available_at, effective_at, unit, currency, rights_class, payload_hash)`. Historical receive times may be unknown: record assumed latency and its provenance separately, never present it as an observed receipt. As-of joins select the most recent version actually available at the decision instant, retaining prior versions and amendments.

## Domain transformation and decision clock

Build fee gap, duration in band, response propensity and net processing cost. Target: incremental net fee dollars minus message labor and attrition loss. Review at 10:00 local market time with benchmark releases and acknowledgments available by 09:55. Use an effective fee only after both contractual acceptance and booking; no retroactive filled proposals. Keep pending announcements distinct from legally effective constraints. Do not train on a later correction, a future completion/outcome or a delisted-only survivor universe.

## Model alternatives

Start with Match yesterday's observable benchmark daily, with contractual limits; also compare a fixed 10-bp band. Then implement Impulse-control dynamic program with survival-calibrated borrower exits. The expensive alternative is Hierarchical Bayesian partially observed control with conservative policy evaluation; it is eligible only after a positive baseline-to-candidate comparison and a sufficient sample. Prefer the baseline if the advanced method's additional complexity does not clear net economic gates.

## Reviewable outputs and fallback

Return hold/reprice recommendation, approved band and counterfactual uncertainty. Save input manifest, time-mask violations, fit window, chosen parameters, cost scenario and reason for every excluded row. No outbound fee message; policy must provide an auditable reason and retain borrower/owner rights as hard constraints. Exceptions return HOLD/BLOCKED and preserve the original decision/book. No adapter may send orders, change contractual prices or upload private records.

## Dependencies and boundaries

Licensed securities-lending fee benchmarks under institution-specific contracts; no verified entitlement or extracts obtained. Complete repricing proposals, accepts/rejects, relationship balances and labor logs; absent. Public feasibility comes first; an absent private adapter is an explicit production blocker, not a justification to synthesize a historical result. Capacity review: Illustrative $400m existing balances; not a new trading strategy. Control concentration and fee elasticity; bps benefit must be net of exits, source revenue sharing and labor. Shared libraries are specified in [TOOLING](TOOLING.md), tests in [EVALS](EVALS.md).
