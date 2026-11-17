# Implementation plan — Collateral Stale-Mark Quarantine and Conservative Valuation

**Scope:** US and euro-area secured financing collateral. No modules described here currently exist in this batch.

## Data contract and architecture

Propose `adapters/collateral_marks.py` => immutable raw manifest => `point_in_time/asof.py` => `collateral_stale_mark_quarantine/features.py` => `baseline.py` / `candidate.py` => `evaluation.py` => review artifact. Native grain is **collateral instrument x mark source x quote/receive event**. Required domain fields: Raw vendor price/event/receive timestamps, currency, clean/dirty convention, coupon accrual, corporate actions, independent quote source and later adjudicated corrections. Public rates and eligible-asset terms support synthetic scenarios, not intraday bond valuation.

The common event envelope is `(entity_id, source_id, source_version, observed_at, published_at, received_at, available_at, effective_at, unit, currency, rights_class, payload_hash)`. Historical receive times may be unknown: record assumed latency and its provenance separately, never present it as an observed receipt. As-of joins select the most recent version actually available at the decision instant, retaining prior versions and amendments.

## Domain transformation and decision clock

Build source age, price convention residual, lineage overlap and conservative interval. Target: underestimated unsecured exposure and false quarantine burden. Gate each mark at ingestion before its use in a financing solve; reference marks must be received earlier than the current solve. Labels are adjudications collected later and assigned only to future model training windows. Keep pending announcements distinct from legally effective constraints. Do not train on a later correction, a future completion/outcome or a delisted-only survivor universe.

## Model alternatives

Start with Use latest received price within a fixed one-day age limit; otherwise last valid mark with static buffer. Then implement Robust cross-source median and asset-specific age/interval rule. The expensive alternative is State-space price filtering with conformal lower valuation bounds and selective quarantine; it is eligible only after a positive baseline-to-candidate comparison and a sufficient sample. Prefer the baseline if the advanced method's additional complexity does not clear net economic gates.

## Reviewable outputs and fallback

Return mark status, safe monitoring valuation, lineage warning and escalation reason. Save input manifest, time-mask violations, fit window, chosen parameters, cost scenario and reason for every excluded row. Target p99 <=100ms per 1,000-mark batch excluding upstream network; missing currency/convention hard-fails. Keep original marks immutable. Exceptions return HOLD/BLOCKED and preserve the original decision/book. No adapter may send orders, change contractual prices or upload private records.

## Dependencies and boundaries

Two independently licensed pricing sources with explicit lineage and correction histories. Authorized collateral marks and independent adjudication records in private infrastructure; absent. Public feasibility comes first; an absent private adapter is an explicit production blocker, not a justification to synthesize a historical result. Capacity review: Illustrative $1bn monitored collateral; benefits are operational hours and conservatively estimated error-loss avoidance, not additive lending alpha. Conservative marks can reduce usable funding capacity. Shared libraries are specified in [TOOLING](TOOLING.md), tests in [EVALS](EVALS.md).
