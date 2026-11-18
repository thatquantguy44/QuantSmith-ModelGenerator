# Evaluation contract — Australian Water Allocation Shadow Price and Crop Basis

**Empirical results: none. All experiment execution is BLOCKED.**

## Primary comparison and falsification

Target: regional crop-margin forecast and hedge basis-adjusted downside loss. Baseline: Seasonal allocation-volume score with a fixed regional crop basket and constant futures hedge ratio. Candidate: Constrained crop-water optimization with allocation-shock local projections. Optional advanced model: Stochastic water/crop dynamic program and robust partial hedge across transfer zones. Metrics: crop-margin MAE, net hedge downside loss, basis risk, transfer-feasibility, water-price interval coverage and turnover. Freeze one primary economic gate and report secondary diagnostics without selectively promoting their successes.

**Objective stop/go:** GO if margin MAE improves >=10% and net hedge downside loss >=5% across >=8 independently held-out seasons/zones; STOP if publication lag eliminates signal or local scarcity has no stable tradable crop exposure.

## Point-in-time and survival controls

Update only after verified allocation announcement; water transaction price enters at public reporting time, not settlement/trade date. Trade a hedge no earlier than next liquid session; use seasons as independent split units. Test observed/published/received/available/effective timestamps independently. Append revisions; never latest-vintage overwrite. Historical ingest latency is an assumption unless recorded. Training-only normalization, feature selection, calibration and parameter selection are mandatory. Keep failed outcomes, terminated contracts, exited instruments and incomplete cohorts with declared censoring; compare the historical eligible universe, not current survivors.

Split chronologically with an embargo at least as long as the maximum target/exposure overlap. Keep issuer/event/season groups together. Require adequate independent clusters before confidence intervals; rows are not independent replications. Log all attempted variants and adjust for selection across the 20-idea research family; holdout failure remains failure.

## Negative tests and operational stress

- Domain fixture: Give identical aggregate water to two disconnected zones: optimization must retain different shadow prices; delaying trade reporting must move its first eligible feature date.
- Future version inserted one second after decision: excluded; missing timestamp/rights: BLOCKED; duplicate payload hash: deduplicated; currency/unit mismatch: rejected.
- Destroy target information with in-group permutation: economic advantage should disappear within declared uncertainty. A solver feasibility test need not disappear, but may not imply alpha.
- Replay source outage, time-zone/DST mismatch, absent instrument and stale quote with explicit HOLD/BLOCKED. Never silently zero-fill unavailable data.
- Double spreads/impact and halve eligible capacity. Illustrative $15m agricultural exposure, small research capacity. Limit futures to <=1% lagged volume; water transactions require separate legal/access review and are not assumed executable by the researcher. Report gross versus net benefits and explain any transition from positive to negative.

## Shadow and production criteria

At least 60 eligible decisions and 90 calendar days, extending through a complete native seasonal/event cycle, with zero hard-constraint/time violations; all overrides and fallback decisions reviewed. Require the primary threshold above plus measured net costs and a verified operational owner. Separate entitlement from allocation units and record ML, hectares and currency explicitly; unknown zone connectivity blocks cross-zone flow. Any unknown legal right or inaccessible input halts promotion. There is no automatic deployment.

## Evidence required in a later results artifact

Code commit, dependency lock hash, immutable source/version manifest, exact split definitions, effective cluster count, baseline/candidate outputs, confidence bounds, cost/capacity scenarios, every negative-test result, rejected rows and signed review state. Academic interest: High interdisciplinary potential, but weak tradable hedge linkage makes this an intentionally lower-priority contrarian project. A theory link or passing synthetic test is not evidence of the hypothesis.
