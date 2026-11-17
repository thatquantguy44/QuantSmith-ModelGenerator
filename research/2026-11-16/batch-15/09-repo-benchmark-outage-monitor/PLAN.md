# Implementation plan — Repo Benchmark Outage and Revision Risk Monitor

**Scope:** United States overnight secured funding. No modules described here currently exist in this batch.

## Data contract and architecture

Propose `adapters/repo_publication_events.py` => immutable raw manifest => `point_in_time/asof.py` => `repo_benchmark_outage_monitor/features.py` => `baseline.py` / `candidate.py` => `evaluation.py` => review artifact. Native grain is **reference rate x publication event x revision version**. Required domain fields: Official rate releases, first-observed timestamps, revision footnotes, contingency notices, rates and ranges; OFR lagged aggregates may inform monitoring but are not contract benchmark substitutes.

The common event envelope is `(entity_id, source_id, source_version, observed_at, published_at, received_at, available_at, effective_at, unit, currency, rights_class, payload_hash)`. Historical receive times may be unknown: record assumed latency and its provenance separately, never present it as an observed receipt. As-of joins select the most recent version actually available at the decision instant, retaining prior versions and amendments.

## Domain transformation and decision clock

Build rate release age, version chain, contingency flag and interval width. Target: reporting error and escalation burden under delayed/corrected publication. Snapshot at 08:15 America/New_York and again after verified revisions; only information received by each timestamp is usable. A 14:30 revision must not overwrite the morning feature snapshot. Keep pending announcements distinct from legally effective constraints. Do not train on a later correction, a future completion/outcome or a delisted-only survivor universe.

## Model alternatives

Start with Carry the most recent official rate and mark missing releases only after end of day. Then implement Versioned publication-state rules plus robust short-horizon rate interval. The expensive alternative is Regime-switching Bayesian filtering with missing-source stress and calibrated selective reporting; it is eligible only after a positive baseline-to-candidate comparison and a sufficient sample. Prefer the baseline if the advanced method's additional complexity does not clear net economic gates.

## Reviewable outputs and fallback

Return accept/interval/review status, immutable as-of report and official-source pointer. Save input manifest, time-mask violations, fit window, chosen parameters, cost scenario and reason for every excluded row. Append-only publication ledger; fail closed on missing source/version and keep synthetic monitoring estimates in a separate schema. Exceptions return HOLD/BLOCKED and preserve the original decision/book. No adapter may send orders, change contractual prices or upload private records.

## Dependencies and boundaries

Optional licensed real-time reference-rate dissemination feed; source-level availability metadata required. Report sensitivities and incident adjudication logs for private testing; absent. Public feasibility comes first; an absent private adapter is an explicit production blocker, not a justification to synthesize a historical result. Capacity review: Illustrative $1bn rate-sensitive monitored exposure; no trading position. Economic value is analyst time and correction effort; excluded speculative avoided trading losses. Shared libraries are specified in [TOOLING](TOOLING.md), tests in [EVALS](EVALS.md).
