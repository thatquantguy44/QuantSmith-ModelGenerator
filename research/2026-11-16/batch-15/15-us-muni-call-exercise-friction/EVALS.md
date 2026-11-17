# Evaluation contract — US Municipal Call-Exercise Friction Surface

**Empirical results: none. All experiment execution is BLOCKED.**

## Primary comparison and falsification

Target: call timing distribution, cash-flow forecast error and duration-adjusted bond return. Baseline: Exercise at first call date when modeled refunding savings exceed a fixed 3% threshold; compare yield-to-worst selection. Candidate: Discrete-time survival model with economic refunding covariates. Optional advanced model: Hierarchical issuer stopping model with financing frictions and cash-flow scenario valuation. Metrics: Brier score, cash-flow MAE, duration error, net matched return, spread/size sensitivity and call calibration. Freeze one primary economic gate and report secondary diagnostics without selectively promoting their successes.

**Objective stop/go:** GO if >=15% cash-flow MAE reduction and >=15 net annualized bps on >=500 held-out call opportunities; STOP if trade-vs-quote bias or missing failed/uncalled bonds explains gains.

## Point-in-time and survival controls

Use only disclosures disseminated by prior close; trade at next obtainable firm offer/bid with a one-session latency. A call notice must enter at publication, not retroactively at the optional call date. Test observed/published/received/available/effective timestamps independently. Append revisions; never latest-vintage overwrite. Historical ingest latency is an assumption unless recorded. Training-only normalization, feature selection, calibration and parameter selection are mandatory. Keep failed outcomes, terminated contracts, exited instruments and incomplete cohorts with declared censoring; compare the historical eligible universe, not current survivors.

Split chronologically with an embargo at least as long as the maximum target/exposure overlap. Keep issuer/event/season groups together. Require adequate independent clusters before confidence intervals; rows are not independent replications. Log all attempted variants and adjust for selection across the 20-idea research family; holdout failure remains failure.

## Negative tests and operational stress

- Domain fixture: Insert a public call notice after the prior-close cutoff: the model must not predict certainty before disclosure. A noncallable bond must have zero optional call hazard.
- Future version inserted one second after decision: excluded; missing timestamp/rights: BLOCKED; duplicate payload hash: deduplicated; currency/unit mismatch: rejected.
- Destroy target information with in-group permutation: economic advantage should disappear within declared uncertainty. A solver feasibility test need not disappear, but may not imply alpha.
- Replay source outage, time-zone/DST mismatch, absent instrument and stale quote with explicit HOLD/BLOCKED. Never silently zero-fill unavailable data.
- Double spreads/impact and halve eligible capacity. Illustrative $40m matched-bond sleeve; cap issue ownership and trade size relative to observed turnover, allow days to execute and charge dealer markup. No presumption of instantaneous municipal execution. Report gross versus net benefits and explain any transition from positive to negative.

## Shadow and production criteria

At least 60 eligible decisions and 90 calendar days, extending through a complete native seasonal/event cycle, with zero hard-constraint/time violations; all overrides and fallback decisions reviewed. Require the primary threshold above plus measured net costs and a verified operational owner. Every parsed call term needs a document page/span; conflicting extraordinary versus optional redemption clauses block valuation. Any unknown legal right or inaccessible input halts promotion. There is no automatic deployment.

## Evidence required in a later results artifact

Code commit, dependency lock hash, immutable source/version manifest, exact split definitions, effective cluster count, baseline/candidate outputs, confidence bounds, cost/capacity scenarios, every negative-test result, rejected rows and signed review state. Academic interest: High: exercise frictions and segmented fixed income; strong public-document reproducibility potential. A theory link or passing synthetic test is not evidence of the hypothesis.
