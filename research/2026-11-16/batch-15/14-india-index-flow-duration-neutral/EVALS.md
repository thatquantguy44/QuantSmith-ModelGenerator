# Evaluation contract — India Bond Index-Flow Saturation

**Empirical results: none. All experiment execution is BLOCKED.**

## Primary comparison and falsification

Target: 20-session inclusion-window residual return and diminishing impact at high ownership. Baseline: Equal-risk inclusion-event basket versus duration-matched eligible controls. Candidate: Matched staggered event study with demand-pressure interactions. Optional advanced model: Doubly robust event design plus a structural price-impact saturation curve. Metrics: net residual bps, pretrend diagnostics, placebo effects, DV01 neutrality, turnover and sensitivity to AUM bounds. Freeze one primary economic gate and report secondary diagnostics without selectively promoting their successes.

**Objective stop/go:** GO if >=20 net annualized bps improvement and event-cluster confidence lower bound >0; pretrends must pass a specified +/-10 bp equivalence band. STOP if fewer than 3 independent cohorts or ownership/AUM histories are reconstructed retrospectively.

## Point-in-time and survival controls

Act next Mumbai session after a verified inclusion announcement or ownership release; close at a predeclared post-effective window. Never use final index weights or future ownership before announcement. Test observed/published/received/available/effective timestamps independently. Append revisions; never latest-vintage overwrite. Historical ingest latency is an assumption unless recorded. Training-only normalization, feature selection, calibration and parameter selection are mandatory. Keep failed outcomes, terminated contracts, exited instruments and incomplete cohorts with declared censoring; compare the historical eligible universe, not current survivors.

Split chronologically with an embargo at least as long as the maximum target/exposure overlap. Keep issuer/event/season groups together. Require adequate independent clusters before confidence intervals; rows are not independent replications. Log all attempted variants and adjust for selection across the 20-idea research family; holdout failure remains failure.

## Negative tests and operational stress

- Domain fixture: Assign the same event to noneligible placebo bonds and to dates six months earlier; no persistent significant effect should survive cohort-level multiple-testing adjustment.
- Future version inserted one second after decision: excluded; missing timestamp/rights: BLOCKED; duplicate payload hash: deduplicated; currency/unit mismatch: rejected.
- Destroy target information with in-group permutation: economic advantage should disappear within declared uncertainty. A solver feasibility test need not disappear, but may not imply alpha.
- Replay source outage, time-zone/DST mismatch, absent instrument and stale quote with explicit HOLD/BLOCKED. Never silently zero-fill unavailable data.
- Double spreads/impact and halve eligible capacity. Illustrative $50m duration-neutral basket, capped at 1% issue turnover with market access and FX hedging charged. Passive flow estimates are not executable demand guarantees. Report gross versus net benefits and explain any transition from positive to negative.

## Shadow and production criteria

At least 60 eligible decisions and 90 calendar days, extending through a complete native seasonal/event cycle, with zero hard-constraint/time violations; all overrides and fallback decisions reviewed. Require the primary threshold above plus measured net costs and a verified operational owner. Announced and effective membership must occupy separate columns; unknown original announcement time blocks that cohort. Any unknown legal right or inaccessible input halts promotion. There is no automatic deployment.

## Evidence required in a later results artifact

Code commit, dependency lock hash, immutable source/version manifest, exact split definitions, effective cluster count, baseline/candidate outputs, confidence bounds, cost/capacity scenarios, every negative-test result, rejected rows and signed review state. Academic interest: High identification interest; scarcity of independent cohorts could make a bounds/survey paper more credible than a causal alpha claim. A theory link or passing synthetic test is not evidence of the hypothesis.
