# Evaluation contract — European Gas Storage Deliverability Hedge

**Empirical results: none. All experiment execution is BLOCKED.**

## Primary comparison and falsification

Target: winter peak procurement tail cost and deliverable MWh shortfall. Baseline: Hedge ratio proportional to national percent-full deficit relative to trailing seasonal average. Candidate: Constrained physical storage network and linear hedge projection. Optional advanced model: Stochastic dynamic storage model with uncertain withdrawal curves and robust hub hedge allocation. Metrics: procurement CVaR, physical shortfall, hedge cost, basis risk, coverage and sensitivity to withdrawal curves. Freeze one primary economic gate and report secondary diagnostics without selectively promoting their successes.

**Objective stop/go:** GO if >=10% CVaR reduction at equal mean cost across >=5 winters including one held-out stressed winter; STOP if results reverse under plausible deliverability curves or cross-border restrictions.

## Point-in-time and survival controls

Recompute after first verified daily publication; execute next liquid hub session with at least one-day lag when historical publication time is unknown. Revised storage values never replace first-release features. Test observed/published/received/available/effective timestamps independently. Append revisions; never latest-vintage overwrite. Historical ingest latency is an assumption unless recorded. Training-only normalization, feature selection, calibration and parameter selection are mandatory. Keep failed outcomes, terminated contracts, exited instruments and incomplete cohorts with declared censoring; compare the historical eligible universe, not current survivors.

Split chronologically with an embargo at least as long as the maximum target/exposure overlap. Keep issuer/event/season groups together. Require adequate independent clusters before confidence intervals; rows are not independent replications. Log all attempted variants and adjust for selection across the 20-idea research family; holdout failure remains failure.

## Negative tests and operational stress

- Domain fixture: Create two facilities with identical percent-full and different withdrawal limits: shortage outputs must differ. Remove one interconnector and forbid unphysical gas flows.
- Future version inserted one second after decision: excluded; missing timestamp/rights: BLOCKED; duplicate payload hash: deduplicated; currency/unit mismatch: rejected.
- Destroy target information with in-group permutation: economic advantage should disappear within declared uncertainty. A solver feasibility test need not disappear, but may not imply alpha.
- Replay source outage, time-zone/DST mismatch, absent instrument and stale quote with explicit HOLD/BLOCKED. Never silently zero-fill unavailable data.
- Double spreads/impact and halve eligible capacity. Illustrative $30m annual hedge exposure; use <=1% lagged hub/spread volume and explicit spread liquidity. USD ROI translates net EUR procurement savings at hedged rates; no assumed storage ownership. Report gross versus net benefits and explain any transition from positive to negative.

## Shadow and production criteria

At least 60 eligible decisions and 90 calendar days, extending through a complete native seasonal/event cycle, with zero hard-constraint/time violations; all overrides and fallback decisions reviewed. Require the primary threshold above plus measured net costs and a verified operational owner. Use gas-day definitions and MWh conversion consistently; data-quality flags propagate to bounds instead of becoming zero inventory. Any unknown legal right or inaccessible input halts promotion. There is no automatic deployment.

## Evidence required in a later results artifact

Code commit, dependency lock hash, immutable source/version manifest, exact split definitions, effective cluster count, baseline/candidate outputs, confidence bounds, cost/capacity scenarios, every negative-test result, rejected rows and signed review state. Academic interest: High: physical deliverability versus headline inventory; falsifiable nonlinear constraints rather than another weather predictor. A theory link or passing synthetic test is not evidence of the hypothesis.
