# 14. India Bond Index-Flow Saturation

**QMG-20261116-14 · B — Domestic/global quant markets · Priority 90/100 (editorial judgment)**

**Geography/instruments:** India government bonds; emerging-market capital flows. **Difficulty:** High. **Production feasibility:** Public event design feasible; index weights, ownership and executable bonds remain data gates. **Effort assumption:** One EM rates researcher plus data engineer for 10-14 weeks.

## Problem, decision and economic value

Index inclusion can produce anticipated buying before a rebalance, but price impact may saturate or reverse when passive demand is already warehoused. **Decision:** Tilt duration-neutral eligible-versus-near-eligible government bond baskets using dated projected passive demand and realized foreign-flow saturation. Economic value is measured through the declared target and net cost model, not forecast accuracy alone.

**Hypothesis (untested):** Expected demand scaled by free-float turnover predicts inclusion-window residual returns better than an inclusion dummy, and improves net basket return by at least 20 bps per annum.

## Mathematics and decision constraints

```text
flow_pressure_it=AUM_known_t*delta_weight_announced_it/free_float_it; R_it=alpha_i+time_t+beta*flow_pressure_it+gamma*ownership_saturation_it+epsilon_it; sum w=0, DV01'w=0, |w_i|<=cap_i
```

AUM_known is a publicly disclosed or licensed contemporaneous index-tracking AUM estimate; delta_weight is announced effective change; free_float excludes known nontrading holders; ownership_saturation uses released ownership/flow data only; w bond positions. Unknown AUM is bounded, never backfilled from later estimates.

Mathematical conventions: one basis point is 0.0001 of annual rate; dt is the declared year fraction. CVaR_a(L)=min_eta[eta+E[(L-eta)^+]/(1-a)] for loss L and tail level a. Risk/turnover penalties are nonnegative and frozen before holdout; rates, prices, cash and face units must reconcile. All forecasts/expectations are conditional on information available at the decision time. A proposed nonlinear or integer formulation is not asserted convex or globally solved without a solver certificate.

## Data and decision timing

RBI FAR/public market context, dated index-provider inclusion/weight notices, foreign ownership/flows, bond eligibility, free-float and issue cash flows; local executable price and hedge history. **Grain:** government bond x announcement/rebalance cohort x public flow release. **Decision clock:** Act next Mumbai session after a verified inclusion announcement or ownership release; close at a predeclared post-effective window. Never use final index weights or future ownership before announcement.

Every input carries observed_at, published_at, received_at, available_at=max(published_at, received_at), effective_at, source/version/hash and rights_class. Unknown historical release time is not reconstructed from a present-day file timestamp; use the declared conservative lag or exclude the row. In replay, separate an assumed historical ingestion latency from an actually recorded receive time. Outcomes may arrive later but cannot be features.

## Model comparison and evaluation

- **Credible baseline:** Equal-risk inclusion-event basket versus duration-matched eligible controls.
- **Suggested candidate:** Matched staggered event study with demand-pressure interactions.
- **Advanced alternative:** Doubly robust event design plus a structural price-impact saturation curve.
- **Target:** 20-session inclusion-window residual return and diminishing impact at high ownership.
- **Metrics:** net residual bps, pretrend diagnostics, placebo effects, DV01 neutrality, turnover and sensitivity to AUM bounds.
- **Pre-registered stop/go:** GO if >=20 net annualized bps improvement and event-cluster confidence lower bound >0; pretrends must pass a specified +/-10 bp equivalence band. STOP if fewer than 3 independent cohorts or ownership/AUM histories are reconstructed retrospectively.
- **Critical negative test:** Assign the same event to noneligible placebo bonds and to dates six months earlier; no persistent significant effect should survive cohort-level multiple-testing adjustment.

Use chronological development/validation/untouched holdout partitions at the native decision frequency, purging the full target horizon and overlapping event groups. Fit transforms, calibration and policy parameters inside training folds. Cluster uncertainty by the economic event/issuer/season, not by repeated rows; preserve disappeared instruments and failed outcomes. Report all candidate variants and correct selection uncertainty. If effective sample size is inadequate, mark BLOCKED rather than lower the gate. Require baseline and candidate to use the same information, risk, liquidity, fees and execution opportunity.

## Capacity and economics

Illustrative $50m duration-neutral basket, capped at 1% issue turnover with market access and FX hedging charged. Passive flow estimates are not executable demand guarantees. Capacity and costs are assumptions until measured at executable sizes. Charge bid/ask, impact, funding, financing/borrow where relevant, settlement costs and the stated operating expense. Double spreads/impact and halve assumed capacity in sensitivity analysis.

**Purely illustrative 24-month ROI; assumptions and arithmetic, not empirical evidence.** USD-equivalent affected exposure $50,000,000; annual net benefit scenarios -10/25/60 bps. Value channel: annual incremental net basket return after bond spreads, FX hedge, access costs and impact. Assume 6 months before benefit starts, 1.5 benefit-years, zero discounting and no terminal value. Two-year all-in engineering/data/review/maintenance cost C=$160,000; this budget is a planning assumption, not a vendor quote. Trading/operating charges are already deducted from scenario benefits; do not deduct them twice.

| Scenario | Annual net benefit before project cost | 24-month benefit B after launch lag | Net ROI (B-C)/C |
|---|---:|---:|---:|
| Downside | $-50,000 | $-75,000 | -146.9% |
| Base | $125,000 | $187,500 | 17.2% |
| Upside | $300,000 | $450,000 | 181.2% |

Break-even annual benefit after launch = $106,667. Full cost is lost if abandoned before benefit; ROI=-100% then. Negative trading/hedge scenarios can be worse than -100%. Utility or avoided-loss scenarios are not guaranteed cash revenue. Budgets and benefits across projects overlap and must not be summed.

## Research value, risk and novelty

**Academic/publication value:** High identification interest; scarcity of independent cohorts could make a bounds/survey paper more credible than a causal alpha claim. **Key risk:** Eligibility correlates with liquidity and issuance; parallel trends may fail. Single historical inclusion episodes cannot support strong causal or scalable trading claims.

**Cumulative novelty check:** Nearest: 2026-11-13/12 EM external funding. This studies security-level mechanical benchmark flows and local relative duration, not country-level currency mismatch or external solvency. Checked against all 35 archived idea READMEs on main; this is a scoped comparison, not certification of originality in academic literature or inaccessible archives.

## Source ladder and truth state

## 1. Public/free first

- [RBI public market-development discussion](https://www.rbi.org.in/scripts/PublicationsView.aspx?Id=23794) — FAR and index-inclusion context; inclusion membership and weights require dated index-provider files. Retrieval run: 2026-11-17T02:38:22+00:00.

## 2. Commercial/licensed

Licensed dated index membership/weights, local bond pricing and public-ownership data distribution rights. Rights, fees, coverage, historical availability and redistribution are **BLOCKED** until reviewed; no entitlement is implied.

## 3. Private/permissioned only after public feasibility

Optional authorized execution records and foreign-investor access approval; absent. Do not upload these records, extracts, identifiers or research results to this public repository. Public outputs use only permitted aggregate summaries or synthetic fixtures reviewed for disclosure.

## 4. Research background

- [Callaway and Sant'Anna, Difference-in-Differences with Multiple Time Periods](https://arxiv.org/abs/1803.09015) — Verified paper title/authors and identification assumptions; does not validate proposed market applications. Retrieval run: 2026-11-17T02:38:22+00:00.

**Evidence classification:** portal/methodology existence was checked through current public search/retrieval. No data download, license clearance, point-in-time panel, calibrated model, price reaction, realized return or ROI was verified. Public accessibility does not grant blanket redistribution. Links support only the statements attached to them; theoretical papers do not support the new hypothesis.


**Status: DESIGN WRITTEN. Empirical execution, data-rights clearance, package lock, runtime, backtest, shadow trial and production implementation: BLOCKED pending the documented prerequisites. No research model was run.**

## Navigation

[SPEC](SPEC.md) · [PLAN](PLAN.md) · [TASKS](TASKS.md) · [ROADMAP](ROADMAP.md) · [HANDOFF](HANDOFF.md) · [SOURCES](SOURCES.md) · [AGENT](AGENT.md) · [SKILL](SKILL.md) · [PROMPT](PROMPT.md) · [TOOLING](TOOLING.md) · [WORKFLOW](WORKFLOW.md) · [RUNTIME](RUNTIME.md) · [EVALS](EVALS.md)
