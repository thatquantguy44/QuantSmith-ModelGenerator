# Evaluation contract — Securities-Loan Dust-Lot Consolidation

**Empirical results: none. All experiment execution is BLOCKED.**

## Primary comparison and falsification

Target: active-ticket count and net servicing-adjusted margin. Baseline: Pro-rata eligible allocation across owners, subject to existing concentration caps. Candidate: Fixed-charge transportation MILP. Optional advanced model: Multi-period lot consolidation with persistence penalties and uncertain demand bands. Metrics: servicing cost, active lots, net revenue, owner fairness constraints, turnover and time to solve. Freeze one primary economic gate and report secondary diagnostics without selectively promoting their successes.

**Objective stop/go:** GO if >=20% servicing-cost saving and <=1% net revenue loss, zero owner-rights violations and payback within 12 months on measured cost inputs. STOP if gains disappear after movement fees or permitted allocations are fixed.

## Point-in-time and survival controls

Solve after confirmed end-of-day books and before next-day instruction cutoff; only booked demand and valid consent known at solve time enter. Settled movements are later outcomes. Test observed/published/received/available/effective timestamps independently. Append revisions; never latest-vintage overwrite. Historical ingest latency is an assumption unless recorded. Training-only normalization, feature selection, calibration and parameter selection are mandatory. Keep failed outcomes, terminated contracts, exited instruments and incomplete cohorts with declared censoring; compare the historical eligible universe, not current survivors.

Split chronologically with an embargo at least as long as the maximum target/exposure overlap. Keep issuer/event/season groups together. Require adequate independent clusters before confidence intervals; rows are not independent replications. Log all attempted variants and adjust for selection across the 20-idea research family; holdout failure remains failure.

## Negative tests and operational stress

- Domain fixture: Set per-ticket cost to zero: consolidation must not invent savings; introduce an owner-specific nontransferability flag and verify its lot remains untouched.
- Future version inserted one second after decision: excluded; missing timestamp/rights: BLOCKED; duplicate payload hash: deduplicated; currency/unit mismatch: rejected.
- Destroy target information with in-group permutation: economic advantage should disappear within declared uncertainty. A solver feasibility test need not disappear, but may not imply alpha.
- Replay source outage, time-zone/DST mismatch, absent instrument and stale quote with explicit HOLD/BLOCKED. Never silently zero-fill unavailable data.
- Double spreads/impact and halve eligible capacity. Illustrative 50,000 serviced lots per year; no market ADV capacity claim. Benefits limited by actual removable lots and movement/consent cost, not gross notional. Report gross versus net benefits and explain any transition from positive to negative.

## Shadow and production criteria

At least 60 eligible decisions and 90 calendar days, extending through a complete native seasonal/event cycle, with zero hard-constraint/time violations; all overrides and fallback decisions reviewed. Require the primary threshold above plus measured net costs and a verified operational owner. Deterministic tie-breaking and original-book fallback on infeasibility; quantity and owner revenue reconcile exactly to declared permitted changes. Any unknown legal right or inaccessible input halts promotion. There is no automatic deployment.

## Evidence required in a later results artifact

Code commit, dependency lock hash, immutable source/version manifest, exact split definitions, effective cluster count, baseline/candidate outputs, confidence bounds, cost/capacity scenarios, every negative-test result, rejected rows and signed review state. Academic interest: Medium: fixed-charge inventory allocation with fair attribution; production engineering likely more valuable than model novelty. A theory link or passing synthetic test is not evidence of the hypothesis.
