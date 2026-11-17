# Evaluation contract — Global Covariance-Break Risk-Budget Controller

**Empirical results: none. All experiment execution is BLOCKED.**

## Primary comparison and falsification

Target: realized risk-contribution tracking error at matched turnover and volatility. Baseline: Monthly risk parity using 60-day EWMA covariance and fixed weight caps; compare a simple shrinkage covariance with no break detection. Candidate: Sequential covariance change detector plus shrinkage and cost-aware no-trade bands. Optional advanced model: Distributionally robust risk-budget optimization over post-break covariance ambiguity sets. Metrics: risk-budget RMSE, realized volatility overshoot, net return, drawdown, turnover and alarm false positives. Freeze one primary economic gate and report secondary diagnostics without selectively promoting their successes.

**Objective stop/go:** GO if risk-budget RMSE falls >=15% and turnover does not rise over >=3 held-out regimes and multiple asynchronous-market assumptions; STOP if improvement is due to more leverage, reduced target risk or tuned crisis dates.

## Point-in-time and survival controls

Decide at 16:30 America/New_York using only completed market sessions and public data received by then; execute each market's next liquid session. Stale Asian observations remain lagged rather than filled with later prices. Test observed/published/received/available/effective timestamps independently. Append revisions; never latest-vintage overwrite. Historical ingest latency is an assumption unless recorded. Training-only normalization, feature selection, calibration and parameter selection are mandatory. Keep failed outcomes, terminated contracts, exited instruments and incomplete cohorts with declared censoring; compare the historical eligible universe, not current survivors.

Split chronologically with an embargo at least as long as the maximum target/exposure overlap. Keep issuer/event/season groups together. Require adequate independent clusters before confidence intervals; rows are not independent replications. Log all attempted variants and adjust for selection across the 20-idea research family; holdout failure remains failure.

## Negative tests and operational stress

- Domain fixture: Delay Japanese returns one extra session and perturb calendar alignment: claimed benefit should remain directionally stable; future-price replacement must fail an availability assertion.
- Future version inserted one second after decision: excluded; missing timestamp/rights: BLOCKED; duplicate payload hash: deduplicated; currency/unit mismatch: rejected.
- Destroy target information with in-group permutation: economic advantage should disappear within declared uncertainty. A solver feasibility test need not disappear, but may not imply alpha.
- Replay source outage, time-zone/DST mismatch, absent instrument and stale quote with explicit HOLD/BLOCKED. Never silently zero-fill unavailable data.
- Double spreads/impact and halve eligible capacity. Illustrative $100m liquid multi-asset allocation; cap <=1% ADV and add market-specific impact, rolls and FX conversion. Capacity derives from instrument liquidity, not covariance model size. Report gross versus net benefits and explain any transition from positive to negative.

## Shadow and production criteria

At least 60 eligible decisions and 90 calendar days, extending through a complete native seasonal/event cycle, with zero hard-constraint/time violations; all overrides and fallback decisions reviewed. Require the primary threshold above plus measured net costs and a verified operational owner. All returns carry local session end and actual receive time; no forward fill across a market closure without a stale flag. Any unknown legal right or inaccessible input halts promotion. There is no automatic deployment.

## Evidence required in a later results artifact

Code commit, dependency lock hash, immutable source/version manifest, exact split definitions, effective cluster count, baseline/candidate outputs, confidence bounds, cost/capacity scenarios, every negative-test result, rejected rows and signed review state. Academic interest: Medium-high: sequential decision value of covariance breaks with asynchronous-market controls; stronger novelty than adding a complex covariance estimator alone. A theory link or passing synthetic test is not evidence of the hypothesis.
