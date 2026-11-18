# Evaluation contract — Brazil Inflation Diffusion versus Breakeven Carry

**Empirical results: none. All experiment execution is BLOCKED.**

## Primary comparison and falsification

Target: 63-session DV01-neutral excess breakeven return net of mechanical carry. Baseline: Carry/roll plus headline inflation surprise using a fixed ridge regression and identical risk budget. Candidate: Sparse distributed-lag regression with local-projection diagnostics. Optional advanced model: Bayesian inflation component state-space model with scenario-robust breakeven sizing. Metrics: out-of-sample MSE, net bps, real/nominal hedge residual, turnover, drawdown and calibration across inflation regimes. Freeze one primary economic gate and report secondary diagnostics without selectively promoting their successes.

**Objective stop/go:** GO if >=10% forecast MSE improvement and >=20 net annualized bps at unchanged risk with >=40 nonoverlapping quarterly outcomes; STOP if official component vintage or executable curve history cannot be established.

## Point-in-time and survival controls

Trade no earlier than next Sao Paulo session after verified inflation and survey publication, with one-hour processing lag. Survey collection dates are never treated as public timestamps. Test observed/published/received/available/effective timestamps independently. Append revisions; never latest-vintage overwrite. Historical ingest latency is an assumption unless recorded. Training-only normalization, feature selection, calibration and parameter selection are mandatory. Keep failed outcomes, terminated contracts, exited instruments and incomplete cohorts with declared censoring; compare the historical eligible universe, not current survivors.

Split chronologically with an embargo at least as long as the maximum target/exposure overlap. Keep issuer/event/season groups together. Require adequate independent clusters before confidence intervals; rows are not independent replications. Log all attempted variants and adjust for selection across the 20-idea research family; holdout failure remains failure.

## Negative tests and operational stress

- Domain fixture: Set nominal and linked yields to parallel shifts with no inflation shock: residual P&L must reflect declared duration mismatch, not be mislabeled inflation alpha.
- Future version inserted one second after decision: excluded; missing timestamp/rights: BLOCKED; duplicate payload hash: deduplicated; currency/unit mismatch: rejected.
- Destroy target information with in-group permutation: economic advantage should disappear within declared uncertainty. A solver feasibility test need not disappear, but may not imply alpha.
- Replay source outage, time-zone/DST mismatch, absent instrument and stale quote with explicit HOLD/BLOCKED. Never silently zero-fill unavailable data.
- Double spreads/impact and halve eligible capacity. Illustrative $40m duration-matched overlay; constrain pair DV01 and <=1% of observed issue turnover. Local liquidity, BRL hedging, indexation and applicable taxes must be priced before investment use. Report gross versus net benefits and explain any transition from positive to negative.

## Shadow and production criteria

At least 60 eligible decisions and 90 calendar days, extending through a complete native seasonal/event cycle, with zero hard-constraint/time violations; all overrides and fallback decisions reviewed. Require the primary threshold above plus measured net costs and a verified operational owner. Unresolved official IPCA component source, tax convention or vintage timestamp blocks any empirical claim; all returns retain BRL and hedged-USD views. Any unknown legal right or inaccessible input halts promotion. There is no automatic deployment.

## Evidence required in a later results artifact

Code commit, dependency lock hash, immutable source/version manifest, exact split definitions, effective cluster count, baseline/candidate outputs, confidence bounds, cost/capacity scenarios, every negative-test result, rejected rows and signed review state. Academic interest: High if public component vintages can be assembled; tests information diffusion separately from mechanical indexation. A theory link or passing synthetic test is not evidence of the hypothesis.
