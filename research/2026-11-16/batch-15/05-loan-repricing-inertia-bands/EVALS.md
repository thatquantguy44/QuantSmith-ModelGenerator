# Evaluation contract — Stock-Loan Repricing Bands with Relationship Friction

**Empirical results: none. All experiment execution is BLOCKED.**

## Primary comparison and falsification

Target: incremental net fee dollars minus message labor and attrition loss. Baseline: Match yesterday's observable benchmark daily, with contractual limits; also compare a fixed 10-bp band. Candidate: Impulse-control dynamic program with survival-calibrated borrower exits. Optional advanced model: Hierarchical Bayesian partially observed control with conservative policy evaluation. Metrics: net margin, retention-adjusted balance, messages per loan, calibration, implementation shortfall and subgroup concentration. Freeze one primary economic gate and report secondary diagnostics without selectively promoting their successes.

**Objective stop/go:** GO if >=5% net revenue improvement with bootstrap lower bound >0 and balance loss <=2% in a pre-registered eligible cohort; no subgroup >5% deterioration. STOP if benefit relies on unobserved rejected requests or violates agreed repricing rights.

## Point-in-time and survival controls

Review at 10:00 local market time with benchmark releases and acknowledgments available by 09:55. Use an effective fee only after both contractual acceptance and booking; no retroactive filled proposals. Test observed/published/received/available/effective timestamps independently. Append revisions; never latest-vintage overwrite. Historical ingest latency is an assumption unless recorded. Training-only normalization, feature selection, calibration and parameter selection are mandatory. Keep failed outcomes, terminated contracts, exited instruments and incomplete cohorts with declared censoring; compare the historical eligible universe, not current survivors.

Split chronologically with an embargo at least as long as the maximum target/exposure overlap. Keep issuer/event/season groups together. Require adequate independent clusters before confidence intervals; rows are not independent replications. Log all attempted variants and adjust for selection across the 20-idea research family; holdout failure remains failure.

## Negative tests and operational stress

- Domain fixture: Set negotiation and exit costs to zero: the optimal inaction band should collapse under an otherwise frictionless model; rejected proposals must never become realized fees.
- Future version inserted one second after decision: excluded; missing timestamp/rights: BLOCKED; duplicate payload hash: deduplicated; currency/unit mismatch: rejected.
- Destroy target information with in-group permutation: economic advantage should disappear within declared uncertainty. A solver feasibility test need not disappear, but may not imply alpha.
- Replay source outage, time-zone/DST mismatch, absent instrument and stale quote with explicit HOLD/BLOCKED. Never silently zero-fill unavailable data.
- Double spreads/impact and halve eligible capacity. Illustrative $400m existing balances; not a new trading strategy. Control concentration and fee elasticity; bps benefit must be net of exits, source revenue sharing and labor. Report gross versus net benefits and explain any transition from positive to negative.

## Shadow and production criteria

At least 60 eligible decisions and 90 calendar days, extending through a complete native seasonal/event cycle, with zero hard-constraint/time violations; all overrides and fallback decisions reviewed. Require the primary threshold above plus measured net costs and a verified operational owner. No outbound fee message; policy must provide an auditable reason and retain borrower/owner rights as hard constraints. Any unknown legal right or inaccessible input halts promotion. There is no automatic deployment.

## Evidence required in a later results artifact

Code commit, dependency lock hash, immutable source/version manifest, exact split definitions, effective cluster count, baseline/candidate outputs, confidence bounds, cost/capacity scenarios, every negative-test result, rejected rows and signed review state. Academic interest: Medium-high: measurable market-design frictions and interpretable control boundaries. A theory link or passing synthetic test is not evidence of the hypothesis.
