# Evaluation contract — Cross-Border Settlement Calendar Bridge Planner

**Empirical results: none. All experiment execution is BLOCKED.**

## Primary comparison and falsification

Target: bridge cash-days and avoidable calendar exceptions. Baseline: Prefund every cross-border obligation two generic business days early, with manual holiday review. Candidate: Time-expanded multi-service cash-flow network. Optional advanced model: Robust network flow with uncertain service extensions and intraday cash arrival bands. Metrics: calendar exceptions, cash-days, funding expense, minimum liquidity and cutoff breaches. Freeze one primary economic gate and report secondary diagnostics without selectively promoting their successes.

**Objective stop/go:** GO if >=90% calendar exceptions avoided and >=10% net bridge-cost saving on >=24 holiday windows; zero infeasible settlement recommendations. STOP if routing assumptions require unapproved service access.

## Point-in-time and survival controls

Plan at least two local business days before a known holiday, using rules announced by then. Unexpected outages are separate stress scenarios; announced future changes enter only after their publication. Test observed/published/received/available/effective timestamps independently. Append revisions; never latest-vintage overwrite. Historical ingest latency is an assumption unless recorded. Training-only normalization, feature selection, calibration and parameter selection are mandatory. Keep failed outcomes, terminated contracts, exited instruments and incomplete cohorts with declared censoring; compare the historical eligible universe, not current survivors.

Split chronologically with an embargo at least as long as the maximum target/exposure overlap. Keep issuer/event/season groups together. Require adequate independent clusters before confidence intervals; rows are not independent replications. Log all attempted variants and adjust for selection across the 20-idea research family; holdout failure remains failure.

## Negative tests and operational stress

- Domain fixture: Replay US/Europe DST mismatch, Good Friday and a service-specific cutoff extension; the planner must distinguish securities and cash service availability.
- Future version inserted one second after decision: excluded; missing timestamp/rights: BLOCKED; duplicate payload hash: deduplicated; currency/unit mismatch: rejected.
- Destroy target information with in-group permutation: economic advantage should disappear within declared uncertainty. A solver feasibility test need not disappear, but may not imply alpha.
- Replay source outage, time-zone/DST mismatch, absent instrument and stale quote with explicit HOLD/BLOCKED. Never silently zero-fill unavailable data.
- Double spreads/impact and halve eligible capacity. Illustrative $200m annual recurring bridge balances in USD equivalent; same approved obligations, no new FX carry position. Saving bounded by actual overlap days and bridge rates. Report gross versus net benefits and explain any transition from positive to negative.

## Shadow and production criteria

At least 60 eligible decisions and 90 calendar days, extending through a complete native seasonal/event cycle, with zero hard-constraint/time violations; all overrides and fallback decisions reviewed. Require the primary threshold above plus measured net costs and a verified operational owner. Timezone-aware UTC storage with local service timezone preserved; unknown calendar version returns BLOCKED, never a guessed weekday. Any unknown legal right or inaccessible input halts promotion. There is no automatic deployment.

## Evidence required in a later results artifact

Code commit, dependency lock hash, immutable source/version manifest, exact split definitions, effective cluster count, baseline/candidate outputs, confidence bounds, cost/capacity scenarios, every negative-test result, rejected rows and signed review state. Academic interest: Medium: formal temporal service graph and reproducible operational errors; high practical portability. A theory link or passing synthetic test is not evidence of the hypothesis.
