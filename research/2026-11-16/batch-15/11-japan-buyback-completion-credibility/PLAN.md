# Implementation plan — Japan Buyback Completion Credibility

**Scope:** Japan listed equities; developed-market event research. No modules described here currently exist in this batch.

## Data contract and architecture

Propose `adapters/japan_buyback_filings.py` => immutable raw manifest => `point_in_time/asof.py` => `japan_buyback_completion_credibility/features.py` => `baseline.py` / `candidate.py` => `evaluation.py` => review artifact. Native grain is **issuer x announced buyback program x filing acceptance event**. Required domain fields: Public issuer/EDINET buyback announcements and monthly completion filings, JPX procedures, cancellation/reissue terms, sector/free-float history, delisted returns and licensed executable prices. J-Quants Pro is a licensed convenience, not assumed free bulk access.

The common event envelope is `(entity_id, source_id, source_version, observed_at, published_at, received_at, available_at, effective_at, unit, currency, rights_class, payload_hash)`. Historical receive times may be unknown: record assumed latency and its provenance separately, never present it as an observed receipt. As-of joins select the most recent version actually available at the decision instant, retaining prior versions and amendments.

## Domain transformation and decision clock

Build prior completion rate, cash-funded capacity, expiry horizon and free-float-normalized authorization. Target: program completion probability and 60-day residual equity return. Enter at next Tokyo session VWAP after a public announcement plus 30 minutes processing; filings arriving after the next-open cutoff shift another session. Completion reports update only when publicly filed. Keep pending announcements distinct from legally effective constraints. Do not train on a later correction, a future completion/outcome or a delisted-only survivor universe.

## Model alternatives

Start with Authorization divided by contemporaneously known float market cap, with the same neutral portfolio and execution rules. Then implement Calibrated discrete-time completion hazard with constrained event portfolio. The expensive alternative is Joint competing-risk completion/cancellation model and doubly robust announcement event analysis; it is eligible only after a positive baseline-to-candidate comparison and a sufficient sample. Prefer the baseline if the advanced method's additional complexity does not clear net economic gates.

## Reviewable outputs and fallback

Return completion probabilities and neutral event-sleeve research orders. Save input manifest, time-mask violations, fit window, chosen parameters, cost scenario and reason for every excluded row. Retain Japanese original text, accession ID and extraction span; any translation/model extraction without supporting span is excluded. Exceptions return HOLD/BLOCKED and preserve the original decision/book. No adapter may send orders, change contractual prices or upload private records.

## Dependencies and boundaries

Licensed Japan total-return/delisting panel and optionally J-Quants Pro filings; redistribution not authorized. Optional privately approved execution logs; unnecessary for a first public/synthetic study. Public feasibility comes first; an absent private adapter is an explicit production blocker, not a justification to synthesize a historical result. Capacity review: Illustrative $25m beta-neutral sleeve; cap each trade at 1% of lagged ADV, use local spreads, impact and shorting costs. Thin small-cap programs may have little scalable edge. Shared libraries are specified in [TOOLING](TOOLING.md), tests in [EVALS](EVALS.md).
