# Evaluation contract — Owner Co-Withdrawal Limits for Lendable Inventory

**Empirical results: none. All experiment execution is BLOCKED.**

## Primary comparison and falsification

Target: joint inventory-shortfall distribution and net cost of an allocation limit. Baseline: Static 10% owner concentration cap with independent withdrawal probabilities. Candidate: Hierarchical common-factor withdrawal model and CVaR allocation. Optional advanced model: Distributionally robust copula stress allocation with mandate-group shocks. Metrics: tail replacement cost, simultaneous-shortfall calibration, revenue retained, stress coverage and concentration. Freeze one primary economic gate and report secondary diagnostics without selectively promoting their successes.

**Objective stop/go:** GO if 99th-percentile cost improves >=15%, normal net revenue loss <=2%, and at least 3 distinct withdrawal episodes are held out; STOP if dependence is unidentified or fewer than 24 months of owner histories exist.

## Point-in-time and survival controls

Set next-day inventory limits after local close using confirmed availability received by cutoff; public fund holdings enter at filing acceptance, not portfolio as-of date. Never condition on the owner's future sale or recall notice. Test observed/published/received/available/effective timestamps independently. Append revisions; never latest-vintage overwrite. Historical ingest latency is an assumption unless recorded. Training-only normalization, feature selection, calibration and parameter selection are mandatory. Keep failed outcomes, terminated contracts, exited instruments and incomplete cohorts with declared censoring; compare the historical eligible universe, not current survivors.

Split chronologically with an embargo at least as long as the maximum target/exposure overlap. Keep issuer/event/season groups together. Require adequate independent clusters before confidence intervals; rows are not independent replications. Log all attempted variants and adjust for selection across the 20-idea research family; holdout failure remains failure.

## Negative tests and operational stress

- Domain fixture: Duplicate an owner under two IDs: effective diversification must not improve; simulate perfect co-withdrawal and verify the model does not report independent-source protection.
- Future version inserted one second after decision: excluded; missing timestamp/rights: BLOCKED; duplicate payload hash: deduplicated; currency/unit mismatch: rejected.
- Destroy target information with in-group permutation: economic advantage should disappear within declared uncertainty. A solver feasibility test need not disappear, but may not imply alpha.
- Replay source outage, time-zone/DST mismatch, absent instrument and stale quote with explicit HOLD/BLOCKED. Never silently zero-fill unavailable data.
- Double spreads/impact and halve eligible capacity. Illustrative $500m supported inventory; direct benefits limited to replacement-cost savings and retained fee revenue. Extreme withdrawals may have no feasible replacement regardless of model. Report gross versus net benefits and explain any transition from positive to negative.

## Shadow and production criteria

At least 60 eligible decisions and 90 calendar days, extending through a complete native seasonal/event cycle, with zero hard-constraint/time violations; all overrides and fallback decisions reviewed. Require the primary threshold above plus measured net costs and a verified operational owner. No raw owner identity or positions in public artifacts; a private run must use pseudonymous IDs and lineage access controls. Any unknown legal right or inaccessible input halts promotion. There is no automatic deployment.

## Evidence required in a later results artifact

Code commit, dependency lock hash, immutable source/version manifest, exact split definitions, effective cluster count, baseline/candidate outputs, confidence bounds, cost/capacity scenarios, every negative-test result, rejected rows and signed review state. Academic interest: High if dependence is identifiable; otherwise honest bounds on inventory diversification are useful internal research. A theory link or passing synthetic test is not evidence of the hypothesis.
