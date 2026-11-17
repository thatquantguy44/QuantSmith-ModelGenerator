# Evaluation contract — Sterling ILTR Auction Demand Smoothing

**Empirical results: none. All experiment execution is BLOCKED.**

## Primary comparison and falsification

Target: cost of a reserve maturity ladder subject to stressed coverage. Baseline: Equal weekly maturities with bids at independently approved maximum willingness-to-pay; compare a single-auction funding plan separately. Candidate: Shape-constrained aggregate supply-curve estimation plus stochastic ladder optimization. Optional advanced model: Partially identified robust auction planning over a set of rival-demand curves. Metrics: GBP funding cost, allocation shortfall, maturity concentration, sensitivity to unobserved demand and bridge usage. Freeze one primary economic gate and report secondary diagnostics without selectively promoting their successes.

**Objective stop/go:** GO if >=1 bp net annualized saving versus equal ladder in >=12 held-out operations and no stressed reserve shortfall. STOP if all plausible demand curves imply the same ladder or savings require underbidding actual willingness-to-pay.

## Point-in-time and survival controls

Use results only after public release; plan by 09:00 Europe/London before an operation using earlier operations and latest approved reserve forecast. Verify each current auction deadline before a live pilot. Test observed/published/received/available/effective timestamps independently. Append revisions; never latest-vintage overwrite. Historical ingest latency is an assumption unless recorded. Training-only normalization, feature selection, calibration and parameter selection are mandatory. Keep failed outcomes, terminated contracts, exited instruments and incomplete cohorts with declared censoring; compare the historical eligible universe, not current survivors.

Split chronologically with an embargo at least as long as the maximum target/exposure overlap. Keep issuer/event/season groups together. Require adequate independent clusters before confidence intervals; rows are not independent replications. Log all attempted variants and adjust for selection across the 20-idea research family; holdout failure remains failure.

## Negative tests and operational stress

- Domain fixture: Replace the estimated supply curve with a flat curve: the model must not claim auction-price savings from moving a price-taking bid.
- Future version inserted one second after decision: excluded; missing timestamp/rights: BLOCKED; duplicate payload hash: deduplicated; currency/unit mismatch: rejected.
- Destroy target information with in-group permutation: economic advantage should disappear within declared uncertainty. A solver feasibility test need not disappear, but may not imply alpha.
- Replay source outage, time-zone/DST mismatch, absent instrument and stale quote with explicit HOLD/BLOCKED. Never silently zero-fill unavailable data.
- Double spreads/impact and halve eligible capacity. Illustrative GBP500m reserve need in USD-equivalent ROI; size must be small relative to auction capacity or explicitly model own impact. Operational access, collateral prepositioning and bridge-funding limits bind. Report gross versus net benefits and explain any transition from positive to negative.

## Shadow and production criteria

At least 60 eligible decisions and 90 calendar days, extending through a complete native seasonal/event cycle, with zero hard-constraint/time violations; all overrides and fallback decisions reviewed. Require the primary threshold above plus measured net costs and a verified operational owner. Every schedule uses Europe/London DST and verified effective facility calibration; missing auction rule version blocks recommendation. Any unknown legal right or inaccessible input halts promotion. There is no automatic deployment.

## Evidence required in a later results artifact

Code commit, dependency lock hash, immutable source/version manifest, exact split definitions, effective cluster count, baseline/candidate outputs, confidence bounds, cost/capacity scenarios, every negative-test result, rejected rows and signed review state. Academic interest: High identification interest, conditional on transparent partial-identification bounds rather than a falsely recovered demand curve. A theory link or passing synthetic test is not evidence of the hypothesis.
