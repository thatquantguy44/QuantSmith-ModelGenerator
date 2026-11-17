# Evaluation contract — US–Europe Corridor Variance and Jump-Risk Budget

**Empirical results: none. All experiment execution is BLOCKED.**

## Primary comparison and falsification

Target: net option-strip carry and stress/tail loss at fixed hedge premium. Baseline: Equal-vega option-strip variance exposure by market with a fixed put-spread tail hedge and identical costs. Candidate: Semiparametric continuous/jump decomposition and constrained risk-budget allocation. Optional advanced model: Distributionally robust jump-diffusion option-portfolio optimization. Metrics: net carry, 99% ES, stress gaps, margin liquidity, hedge slippage, vega and Greeks. Freeze one primary economic gate and report secondary diagnostics without selectively promoting their successes.

**Objective stop/go:** GO if >=15% ES reduction with mean net carry within 5% of baseline across >=8 years including held-out stress; STOP if benefit fails under doubled option spreads or cannot be implemented by listed strips.

## Point-in-time and survival controls

Allocate at a common UTC snapshot when both markets have liquid executable quotes; use prior completed return bars only. Do not pair a European close with later US data as contemporaneous. Test observed/published/received/available/effective timestamps independently. Append revisions; never latest-vintage overwrite. Historical ingest latency is an assumption unless recorded. Training-only normalization, feature selection, calibration and parameter selection are mandatory. Keep failed outcomes, terminated contracts, exited instruments and incomplete cohorts with declared censoring; compare the historical eligible universe, not current survivors.

Split chronologically with an embargo at least as long as the maximum target/exposure overlap. Keep issuer/event/season groups together. Require adequate independent clusters before confidence intervals; rows are not independent replications. Log all attempted variants and adjust for selection across the 20-idea research family; holdout failure remains failure.

## Negative tests and operational stress

- Domain fixture: Insert a large overnight gap with no intraday prints: loss and jump exposure must remain visible; an apparent free option caused by zero/stale bid must be rejected.
- Future version inserted one second after decision: excluded; missing timestamp/rights: BLOCKED; duplicate payload hash: deduplicated; currency/unit mismatch: rejected.
- Destroy target information with in-group permutation: economic advantage should disappear within declared uncertainty. A solver feasibility test need not disappear, but may not imply alpha.
- Replay source outage, time-zone/DST mismatch, absent instrument and stale quote with explicit HOLD/BLOCKED. Never silently zero-fill unavailable data.
- Double spreads/impact and halve eligible capacity. Illustrative $20m capital budget with explicit vega/margin limits, <=1% option-strike volume/open-interest bounds and no unlimited tail-risk assumption. Capacity likely concentrated in a few liquid expiries. Report gross versus net benefits and explain any transition from positive to negative.

## Shadow and production criteria

At least 60 eligible decisions and 90 calendar days, extending through a complete native seasonal/event cycle, with zero hard-constraint/time violations; all overrides and fallback decisions reviewed. Require the primary threshold above plus measured net costs and a verified operational owner. Reject crossed/stale quotes and impossible option monotonicity; no interpolation may create executable liquidity that was not quoted. Any unknown legal right or inaccessible input halts promotion. There is no automatic deployment.

## Evidence required in a later results artifact

Code commit, dependency lock hash, immutable source/version manifest, exact split definitions, effective cluster count, baseline/candidate outputs, confidence bounds, cost/capacity scenarios, every negative-test result, rejected rows and signed review state. Academic interest: High methodological potential; a crowded literature means exact corridor and jump novelty needs further review. A theory link or passing synthetic test is not evidence of the hypothesis.
