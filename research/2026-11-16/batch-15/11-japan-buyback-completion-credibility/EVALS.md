# Evaluation contract — Japan Buyback Completion Credibility

**Empirical results: none. All experiment execution is BLOCKED.**

## Primary comparison and falsification

Target: program completion probability and 60-day residual equity return. Baseline: Authorization divided by contemporaneously known float market cap, with the same neutral portfolio and execution rules. Candidate: Calibrated discrete-time completion hazard with constrained event portfolio. Optional advanced model: Joint competing-risk completion/cancellation model and doubly robust announcement event analysis. Metrics: Brier score, calibration, residual net return, turnover, drawdown, participation and exposure neutrality. Freeze one primary economic gate and report secondary diagnostics without selectively promoting their successes.

**Objective stop/go:** GO if completion Brier improves >=10% and net return uplift >=50 annualized bps with block-bootstrap lower bound >0 over >=200 programs and a held-out year; STOP on missing delistings or gains concentrated in inaccessible prints.

## Point-in-time and survival controls

Enter at next Tokyo session VWAP after a public announcement plus 30 minutes processing; filings arriving after the next-open cutoff shift another session. Completion reports update only when publicly filed. Test observed/published/received/available/effective timestamps independently. Append revisions; never latest-vintage overwrite. Historical ingest latency is an assumption unless recorded. Training-only normalization, feature selection, calibration and parameter selection are mandatory. Keep failed outcomes, terminated contracts, exited instruments and incomplete cohorts with declared censoring; compare the historical eligible universe, not current survivors.

Split chronologically with an embargo at least as long as the maximum target/exposure overlap. Keep issuer/event/season groups together. Require adequate independent clusters before confidence intervals; rows are not independent replications. Log all attempted variants and adjust for selection across the 20-idea research family; holdout failure remains failure.

## Negative tests and operational stress

- Domain fixture: Shift completion filings to their reporting-period end: leakage checker must reject the join; include terminated programs and delisted issuers with zero future authorization assumed.
- Future version inserted one second after decision: excluded; missing timestamp/rights: BLOCKED; duplicate payload hash: deduplicated; currency/unit mismatch: rejected.
- Destroy target information with in-group permutation: economic advantage should disappear within declared uncertainty. A solver feasibility test need not disappear, but may not imply alpha.
- Replay source outage, time-zone/DST mismatch, absent instrument and stale quote with explicit HOLD/BLOCKED. Never silently zero-fill unavailable data.
- Double spreads/impact and halve eligible capacity. Illustrative $25m beta-neutral sleeve; cap each trade at 1% of lagged ADV, use local spreads, impact and shorting costs. Thin small-cap programs may have little scalable edge. Report gross versus net benefits and explain any transition from positive to negative.

## Shadow and production criteria

At least 60 eligible decisions and 90 calendar days, extending through a complete native seasonal/event cycle, with zero hard-constraint/time violations; all overrides and fallback decisions reviewed. Require the primary threshold above plus measured net costs and a verified operational owner. Retain Japanese original text, accession ID and extraction span; any translation/model extraction without supporting span is excluded. Any unknown legal right or inaccessible input halts promotion. There is no automatic deployment.

## Evidence required in a later results artifact

Code commit, dependency lock hash, immutable source/version manifest, exact split definitions, effective cluster count, baseline/candidate outputs, confidence bounds, cost/capacity scenarios, every negative-test result, rejected rows and signed review state. Academic interest: High: completion credibility and execution mechanism heterogeneity; causal claims require stronger identification than prediction. A theory link or passing synthetic test is not evidence of the hypothesis.
