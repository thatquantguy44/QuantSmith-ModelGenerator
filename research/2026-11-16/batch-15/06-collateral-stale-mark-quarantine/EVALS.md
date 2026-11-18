# Evaluation contract — Collateral Stale-Mark Quarantine and Conservative Valuation

**Empirical results: none. All experiment execution is BLOCKED.**

## Primary comparison and falsification

Target: underestimated unsecured exposure and false quarantine burden. Baseline: Use latest received price within a fixed one-day age limit; otherwise last valid mark with static buffer. Candidate: Robust cross-source median and asset-specific age/interval rule. Optional advanced model: State-space price filtering with conformal lower valuation bounds and selective quarantine. Metrics: value shortfall, interval coverage, false positives, stale detection delay, desk override rate and review hours. Freeze one primary economic gate and report secondary diagnostics without selectively promoting their successes.

**Objective stop/go:** GO if underestimation falls >=30%, clean-mark false quarantine <1%, and lower-bound coverage >=99% in stress replay; reject if benefit comes only from excessive haircuts or review burden exceeds 0.5 FTE per 10k instruments.

## Point-in-time and survival controls

Gate each mark at ingestion before its use in a financing solve; reference marks must be received earlier than the current solve. Labels are adjudications collected later and assigned only to future model training windows. Test observed/published/received/available/effective timestamps independently. Append revisions; never latest-vintage overwrite. Historical ingest latency is an assumption unless recorded. Training-only normalization, feature selection, calibration and parameter selection are mandatory. Keep failed outcomes, terminated contracts, exited instruments and incomplete cohorts with declared censoring; compare the historical eligible universe, not current survivors.

Split chronologically with an embargo at least as long as the maximum target/exposure overlap. Keep issuer/event/season groups together. Require adequate independent clusters before confidence intervals; rows are not independent replications. Log all attempted variants and adjust for selection across the 20-idea research family; holdout failure remains failure.

## Negative tests and operational stress

- Domain fixture: Inject a 100x currency/unit error, stale timestamp, ex-coupon drop and two nominally independent marks with identical upstream provenance; detect unit/staleness defects while preserving valid convention changes.
- Future version inserted one second after decision: excluded; missing timestamp/rights: BLOCKED; duplicate payload hash: deduplicated; currency/unit mismatch: rejected.
- Destroy target information with in-group permutation: economic advantage should disappear within declared uncertainty. A solver feasibility test need not disappear, but may not imply alpha.
- Replay source outage, time-zone/DST mismatch, absent instrument and stale quote with explicit HOLD/BLOCKED. Never silently zero-fill unavailable data.
- Double spreads/impact and halve eligible capacity. Illustrative $1bn monitored collateral; benefits are operational hours and conservatively estimated error-loss avoidance, not additive lending alpha. Conservative marks can reduce usable funding capacity. Report gross versus net benefits and explain any transition from positive to negative.

## Shadow and production criteria

At least 60 eligible decisions and 90 calendar days, extending through a complete native seasonal/event cycle, with zero hard-constraint/time violations; all overrides and fallback decisions reviewed. Require the primary threshold above plus measured net costs and a verified operational owner. Target p99 <=100ms per 1,000-mark batch excluding upstream network; missing currency/convention hard-fails. Keep original marks immutable. Any unknown legal right or inaccessible input halts promotion. There is no automatic deployment.

## Evidence required in a later results artifact

Code commit, dependency lock hash, immutable source/version manifest, exact split definitions, effective cluster count, baseline/candidate outputs, confidence bounds, cost/capacity scenarios, every negative-test result, rejected rows and signed review state. Academic interest: Medium: reproducible error taxonomy and dependence-aware coverage; strongest value may be operational rather than journal novelty. A theory link or passing synthetic test is not evidence of the hypothesis.
