# Evaluation contract — Repo Benchmark Outage and Revision Risk Monitor

**Empirical results: none. All experiment execution is BLOCKED.**

## Primary comparison and falsification

Target: reporting error and escalation burden under delayed/corrected publication. Baseline: Carry the most recent official rate and mark missing releases only after end of day. Candidate: Versioned publication-state rules plus robust short-horizon rate interval. Optional advanced model: Regime-switching Bayesian filtering with missing-source stress and calibrated selective reporting. Metrics: basis-point error, dollar sensitivity error, interval coverage, false escalations, detection latency and audit completeness. Freeze one primary economic gate and report secondary diagnostics without selectively promoting their successes.

**Objective stop/go:** GO if >=50% reduction in material (>2 bp monitoring error) incidents and <2% false escalation over >=250 releases plus synthetic outages; interval coverage >=99%. STOP if rare-event evidence cannot separate improvement from excessive review.

## Point-in-time and survival controls

Snapshot at 08:15 America/New_York and again after verified revisions; only information received by each timestamp is usable. A 14:30 revision must not overwrite the morning feature snapshot. Test observed/published/received/available/effective timestamps independently. Append revisions; never latest-vintage overwrite. Historical ingest latency is an assumption unless recorded. Training-only normalization, feature selection, calibration and parameter selection are mandatory. Keep failed outcomes, terminated contracts, exited instruments and incomplete cohorts with declared censoring; compare the historical eligible universe, not current survivors.

Split chronologically with an embargo at least as long as the maximum target/exposure overlap. Keep issuer/event/season groups together. Require adequate independent clusters before confidence intervals; rows are not independent replications. Log all attempted variants and adjust for selection across the 20-idea research family; holdout failure remains failure.

## Negative tests and operational stress

- Domain fixture: Hide a morning release and reveal a later correction: morning output must stay immutable and explicitly uncertain; no synthetic estimate may populate a contractual-rate field.
- Future version inserted one second after decision: excluded; missing timestamp/rights: BLOCKED; duplicate payload hash: deduplicated; currency/unit mismatch: rejected.
- Destroy target information with in-group permutation: economic advantage should disappear within declared uncertainty. A solver feasibility test need not disappear, but may not imply alpha.
- Replay source outage, time-zone/DST mismatch, absent instrument and stale quote with explicit HOLD/BLOCKED. Never silently zero-fill unavailable data.
- Double spreads/impact and halve eligible capacity. Illustrative $1bn rate-sensitive monitored exposure; no trading position. Economic value is analyst time and correction effort; excluded speculative avoided trading losses. Report gross versus net benefits and explain any transition from positive to negative.

## Shadow and production criteria

At least 60 eligible decisions and 90 calendar days, extending through a complete native seasonal/event cycle, with zero hard-constraint/time violations; all overrides and fallback decisions reviewed. Require the primary threshold above plus measured net costs and a verified operational owner. Append-only publication ledger; fail closed on missing source/version and keep synthetic monitoring estimates in a separate schema. Any unknown legal right or inaccessible input halts promotion. There is no automatic deployment.

## Evidence required in a later results artifact

Code commit, dependency lock hash, immutable source/version manifest, exact split definitions, effective cluster count, baseline/candidate outputs, confidence bounds, cost/capacity scenarios, every negative-test result, rejected rows and signed review state. Academic interest: Medium: benchmark-data resilience and reproducible counterfactual outages; rare events limit generalization. A theory link or passing synthetic test is not evidence of the hypothesis.
