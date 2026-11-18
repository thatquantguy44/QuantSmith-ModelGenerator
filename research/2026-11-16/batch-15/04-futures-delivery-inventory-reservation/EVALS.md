# Evaluation contract — Treasury Futures Delivery Inventory Reservation

**Empirical results: none. All experiment execution is BLOCKED.**

## Primary comparison and falsification

Target: net lending revenue plus delivery economics for a fixed pre-existing futures obligation. Baseline: Hold back 10% of eligible basket inventory and allocate remaining loans using current fees. Candidate: Scenario dynamic programming for marginal delivery-option value. Optional advanced model: Least-squares Monte Carlo with joint cash/futures/repo scenarios and integer delivery sizing. Metrics: total net economics, forced replacement, delivery feasibility, hedge error and option-value stability. Freeze one primary economic gate and report secondary diagnostics without selectively promoting their successes.

**Objective stop/go:** GO if >=2 annualized bps saving over fixed holdback across >=8 delivery cycles, no missed delivery and positive benefit at twice observed transaction costs. STOP if gains depend on hindsight cheapest-to-deliver identity.

## Point-in-time and survival controls

Reserve at 15:00 America/Chicago using quotes available by 14:55 and current contract basket version; subsequent delivery notices are outcomes, never predictive features. Test observed/published/received/available/effective timestamps independently. Append revisions; never latest-vintage overwrite. Historical ingest latency is an assumption unless recorded. Training-only normalization, feature selection, calibration and parameter selection are mandatory. Keep failed outcomes, terminated contracts, exited instruments and incomplete cohorts with declared censoring; compare the historical eligible universe, not current survivors.

Split chronologically with an embargo at least as long as the maximum target/exposure overlap. Keep issuer/event/season groups together. Require adequate independent clusters before confidence intervals; rows are not independent replications. Log all attempted variants and adjust for selection across the 20-idea research family; holdout failure remains failure.

## Negative tests and operational stress

- Domain fixture: Freeze the basket to a single security: option-selection value must vanish; change conversion factor units and require invoice identity failure rather than silent rescaling.
- Future version inserted one second after decision: excluded; missing timestamp/rights: BLOCKED; duplicate payload hash: deduplicated; currency/unit mismatch: rejected.
- Destroy target information with in-group permutation: economic advantage should disappear within declared uncertainty. A solver feasibility test need not disappear, but may not imply alpha.
- Replay source outage, time-zone/DST mismatch, absent instrument and stale quote with explicit HOLD/BLOCKED. Never silently zero-fill unavailable data.
- Double spreads/impact and halve eligible capacity. Illustrative $250m affected deliverable inventory. Limited by futures obligation size and deliverable-lot depth; do not take a new directional basis trade merely to generate lending revenue. Report gross versus net benefits and explain any transition from positive to negative.

## Shadow and production criteria

At least 60 eligible decisions and 90 calendar days, extending through a complete native seasonal/event cycle, with zero hard-constraint/time violations; all overrides and fallback decisions reviewed. Require the primary threshold above plus measured net costs and a verified operational owner. Contract units, invoice rounding and delivery rules must be versioned and independently reconciled before optimization. Any unknown legal right or inaccessible input halts promotion. There is no automatic deployment.

## Evidence required in a later results artifact

Code commit, dependency lock hash, immutable source/version manifest, exact split definitions, effective cluster count, baseline/candidate outputs, confidence bounds, cost/capacity scenarios, every negative-test result, rejected rows and signed review state. Academic interest: High: interaction of delivery options and lending availability; empirical claim requires licensed synchronized markets. A theory link or passing synthetic test is not evidence of the hypothesis.
