# Implementation plan — ECB Collateral Eligibility-Cliff Prepositioning

**Scope:** Euro area; EUR marketable collateral. No modules described here currently exist in this batch.

## Data contract and architecture

Propose `adapters/ecb_eligibility.py` => immutable raw manifest => `point_in_time/asof.py` => `ecb_eligibility_cliff_prepositioning/features.py` => `baseline.py` / `candidate.py` => `evaluation.py` => review artifact. Native grain is **ISIN x release version x effective date**. Required domain fields: ECB full/delta eligibility files, announcement timestamps, effective dates, maturity, haircuts, issuer mapping, replacement prices and settlement windows. Do not infer a future delisting from a later archive snapshot.

The common event envelope is `(entity_id, source_id, source_version, observed_at, published_at, received_at, available_at, effective_at, unit, currency, rights_class, payload_hash)`. Historical receive times may be unknown: record assumed latency and its provenance separately, never present it as an observed receipt. As-of joins select the most recent version actually available at the decision instant, retaining prior versions and amendments.

## Domain transformation and decision clock

Build announced future eligibility matrix, haircut-adjusted coverage and replacement ladder. Target: replacement implementation cost and eligible-value shortfall. Evaluate after verified ECB publication and ingestion, with a minimum 30-minute operational latency; any action is next eligible settlement window. Historical daily snapshots without timestamp proof are usable only with a conservative next-business-day decision lag. Keep pending announcements distinct from legally effective constraints. Do not train on a later correction, a future completion/outcome or a delisted-only survivor universe.

## Model alternatives

Start with Replace only at maturity or first effective ineligibility date using cheapest currently eligible asset. Then implement Rolling-horizon linear allocation using announced eligibility transitions. The expensive alternative is Distributionally robust prepositioning under uncertain unannounced eligibility loss; it is eligible only after a positive baseline-to-candidate comparison and a sufficient sample. Prefer the baseline if the advanced method's additional complexity does not clear net economic gates.

## Reviewable outputs and fallback

Return dated replacement schedule and coverage stress certificate. Save input manifest, time-mask violations, fit window, chosen parameters, cost scenario and reason for every excluded row. Preserve source byte hashes and schema versions; reject any unknown CHANGE code or missing effective date instead of guessing. Exceptions return HOLD/BLOCKED and preserve the original decision/book. No adapter may send orders, change contractual prices or upload private records.

## Dependencies and boundaries

Licensed EUR bond bid/ask and historical rating/terms data; no vendor extracts in the public repository. Institution-approved eligibility, holdings and transfer permissions; absent. Public feasibility comes first; an absent private adapter is an explicit production blocker, not a justification to synthesize a historical result. Capacity review: Illustrative EUR500m affected annual balances, converted to USD equivalent for ROI. Limited by replacement-asset depth, settlement access and concentration limits; use <=1% observed daily turnover until calibrated. Shared libraries are specified in [TOOLING](TOOLING.md), tests in [EVALS](EVALS.md).
