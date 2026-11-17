# Evaluation contract — ECB Collateral Eligibility-Cliff Prepositioning

**Empirical results: none. All experiment execution is BLOCKED.**

## Primary comparison and falsification

Target: replacement implementation cost and eligible-value shortfall. Baseline: Replace only at maturity or first effective ineligibility date using cheapest currently eligible asset. Candidate: Rolling-horizon linear allocation using announced eligibility transitions. Optional advanced model: Distributionally robust prepositioning under uncertain unannounced eligibility loss. Metrics: net carry/transfer expense, shortfall, false early replacements, turnover and issuer concentration. Freeze one primary economic gate and report secondary diagnostics without selectively promoting their successes.

**Objective stop/go:** GO if cost saving >=2 annualized bps on affected balances and zero eligibility violations across >=20 independent transition clusters; worst stress shortfall no larger than baseline. STOP if timestamp-safe sample is inadequate or cost rises under doubled bid/ask.

## Point-in-time and survival controls

Evaluate after verified ECB publication and ingestion, with a minimum 30-minute operational latency; any action is next eligible settlement window. Historical daily snapshots without timestamp proof are usable only with a conservative next-business-day decision lag. Test observed/published/received/available/effective timestamps independently. Append revisions; never latest-vintage overwrite. Historical ingest latency is an assumption unless recorded. Training-only normalization, feature selection, calibration and parameter selection are mandatory. Keep failed outcomes, terminated contracts, exited instruments and incomplete cohorts with declared censoring; compare the historical eligible universe, not current survivors.

Split chronologically with an embargo at least as long as the maximum target/exposure overlap. Keep issuer/event/season groups together. Require adequate independent clusters before confidence intervals; rows are not independent replications. Log all attempted variants and adjust for selection across the 20-idea research family; holdout failure remains failure.

## Negative tests and operational stress

- Domain fixture: Move an announcement after the decision timestamp: all corresponding anticipatory trades must disappear; maturity may remain predictable from previously published terms.
- Future version inserted one second after decision: excluded; missing timestamp/rights: BLOCKED; duplicate payload hash: deduplicated; currency/unit mismatch: rejected.
- Destroy target information with in-group permutation: economic advantage should disappear within declared uncertainty. A solver feasibility test need not disappear, but may not imply alpha.
- Replay source outage, time-zone/DST mismatch, absent instrument and stale quote with explicit HOLD/BLOCKED. Never silently zero-fill unavailable data.
- Double spreads/impact and halve eligible capacity. Illustrative EUR500m affected annual balances, converted to USD equivalent for ROI. Limited by replacement-asset depth, settlement access and concentration limits; use <=1% observed daily turnover until calibrated. Report gross versus net benefits and explain any transition from positive to negative.

## Shadow and production criteria

At least 60 eligible decisions and 90 calendar days, extending through a complete native seasonal/event cycle, with zero hard-constraint/time violations; all overrides and fallback decisions reviewed. Require the primary threshold above plus measured net costs and a verified operational owner. Preserve source byte hashes and schema versions; reject any unknown CHANGE code or missing effective date instead of guessing. Any unknown legal right or inaccessible input halts promotion. There is no automatic deployment.

## Evidence required in a later results artifact

Code commit, dependency lock hash, immutable source/version manifest, exact split definitions, effective cluster count, baseline/candidate outputs, confidence bounds, cost/capacity scenarios, every negative-test result, rejected rows and signed review state. Academic interest: Medium-high: event-time collateral option value, with public framework changes and transparent effective-time tests. A theory link or passing synthetic test is not evidence of the hypothesis.
