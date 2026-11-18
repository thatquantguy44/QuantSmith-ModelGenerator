# 13. European Gas Storage Deliverability Hedge

**QMG-20261116-13 · B — Domestic/global quant markets · Priority 89/100 (editorial judgment)**

**Geography/instruments:** Germany, Netherlands, Italy and European gas hubs. **Difficulty:** High. **Production feasibility:** Public physical-data model feasible; TTF/hub hedge testing requires licensed curves. **Effort assumption:** One energy researcher and one engineer for 10-14 weeks.

## Problem, decision and economic value

Equal storage fill percentages can imply different peak withdrawal capacity, making inventory-only shortage hedges economically misleading. **Decision:** Hedge winter peak gas-delivery risk using facility-level withdrawal constraints rather than national percent-full alone. Economic value is measured through the declared target and net cost model, not forecast accuracy alone.

**Hypothesis (untested):** A deliverability-weighted storage index reduces winter peak procurement CVaR by at least 10% versus a percent-full rule at equal average hedge cost.

## Mathematics and decision constraints

```text
min_(u,s) sum_t pi_t*s_t; sum_i u_it+s_t>=D_t, 0<=u_it<=g_i(S_it), S_i,t+1=S_it+injection_it-u_it, 0<=S_it<=capacity_i, pipe_flow<=pipe_capacity; hedge=min_h E[cost(h)] + lambda*CVaR_95(cost(h)), |h|<=H
```

S inventory in MWh; u withdrawal MWh/day; g inventory-dependent deliverability; s shortage MWh; D stressed delivered demand; pi shortage penalty per MWh; i facility; t gas day; injection is an exogenous scenario flow; h hub futures/seasonal spread hedge; H risk/participation cap. Physical flows obey hub connectivity and pipe limits; physical optimization informs shortage exposure, not a claim of storage operating rights.

Mathematical conventions: one basis point is 0.0001 of annual rate; dt is the declared year fraction. CVaR_a(L)=min_eta[eta+E[(L-eta)^+]/(1-a)] for loss L and tail level a. Risk/turnover penalties are nonnegative and frozen before holdout; rates, prices, cash and face units must reconcile. All forecasts/expectations are conditional on information available at the decision time. A proposed nonlinear or integer formulation is not asserted convex or globally solved without a solver certificate.

## Data and decision timing

GIE published facility stocks/capacities/data-quality flags, publication versions, hub connectivity and outage notices; inventory-dependent performance curves need validated operator data or explicitly bounded assumptions. Licensed day-ahead/futures curves for hedging. **Grain:** storage facility x gas day x publication version. **Decision clock:** Recompute after first verified daily publication; execute next liquid hub session with at least one-day lag when historical publication time is unknown. Revised storage values never replace first-release features.

Every input carries observed_at, published_at, received_at, available_at=max(published_at, received_at), effective_at, source/version/hash and rights_class. Unknown historical release time is not reconstructed from a present-day file timestamp; use the declared conservative lag or exclude the row. In replay, separate an assumed historical ingestion latency from an actually recorded receive time. Outcomes may arrive later but cannot be features.

## Model comparison and evaluation

- **Credible baseline:** Hedge ratio proportional to national percent-full deficit relative to trailing seasonal average.
- **Suggested candidate:** Constrained physical storage network and linear hedge projection.
- **Advanced alternative:** Stochastic dynamic storage model with uncertain withdrawal curves and robust hub hedge allocation.
- **Target:** winter peak procurement tail cost and deliverable MWh shortfall.
- **Metrics:** procurement CVaR, physical shortfall, hedge cost, basis risk, coverage and sensitivity to withdrawal curves.
- **Pre-registered stop/go:** GO if >=10% CVaR reduction at equal mean cost across >=5 winters including one held-out stressed winter; STOP if results reverse under plausible deliverability curves or cross-border restrictions.
- **Critical negative test:** Create two facilities with identical percent-full and different withdrawal limits: shortage outputs must differ. Remove one interconnector and forbid unphysical gas flows.

Use chronological development/validation/untouched holdout partitions at the native decision frequency, purging the full target horizon and overlapping event groups. Fit transforms, calibration and policy parameters inside training folds. Cluster uncertainty by the economic event/issuer/season, not by repeated rows; preserve disappeared instruments and failed outcomes. Report all candidate variants and correct selection uncertainty. If effective sample size is inadequate, mark BLOCKED rather than lower the gate. Require baseline and candidate to use the same information, risk, liquidity, fees and execution opportunity.

## Capacity and economics

Illustrative $30m annual hedge exposure; use <=1% lagged hub/spread volume and explicit spread liquidity. USD ROI translates net EUR procurement savings at hedged rates; no assumed storage ownership. Capacity and costs are assumptions until measured at executable sizes. Charge bid/ask, impact, funding, financing/borrow where relevant, settlement costs and the stated operating expense. Double spreads/impact and halve assumed capacity in sensitivity analysis.

**Purely illustrative 24-month ROI; assumptions and arithmetic, not empirical evidence.** USD-equivalent affected exposure $30,000,000; annual net benefit scenarios -10/40/100 bps. Value channel: annual incremental procurement/hedge savings net of futures costs and hub basis slippage. Assume 6 months before benefit starts, 1.5 benefit-years, zero discounting and no terminal value. Two-year all-in engineering/data/review/maintenance cost C=$170,000; this budget is a planning assumption, not a vendor quote. Trading/operating charges are already deducted from scenario benefits; do not deduct them twice.

| Scenario | Annual net benefit before project cost | 24-month benefit B after launch lag | Net ROI (B-C)/C |
|---|---:|---:|---:|
| Downside | $-30,000 | $-45,000 | -126.5% |
| Base | $120,000 | $180,000 | 5.9% |
| Upside | $300,000 | $450,000 | 164.7% |

Break-even annual benefit after launch = $113,333. Full cost is lost if abandoned before benefit; ROI=-100% then. Negative trading/hedge scenarios can be worse than -100%. Utility or avoided-loss scenarios are not guaranteed cash revenue. Budgets and benefits across projects overlap and must not be summed.

## Research value, risk and novelty

**Academic/publication value:** High: physical deliverability versus headline inventory; falsifiable nonlinear constraints rather than another weather predictor. **Key risk:** Reported maximum withdrawal is not necessarily sustainable at low fill. Regional bottlenecks and revisions dominate; proxy futures do not deliver facility access.

**Cumulative novelty check:** Nearest: 2026-11-13/17 weather-energy revisions. Weather forecasts are held fixed here; the new state variable is inventory-dependent withdrawal deliverability and geographic transfer capacity. Checked against all 35 archived idea READMEs on main; this is a scoped comparison, not certification of originality in academic literature or inaccessible archives.

## Source ladder and truth state

## 1. Public/free first

- [GIE storage database](https://www.gie.eu/transparency/databases/storage-database/) — Facility capacities and storage database; terms, registration, reporting changes and historical snapshots require audit. Retrieval run: 2026-11-17T02:38:22+00:00.
- [GIE AGSI/ALSI API documentation](https://www.gie.eu/transparency-platform/GIE_API_documentation_v007.pdf) — API and data-quality documentation; free access does not imply unrestricted redistribution. No key provisioned. Retrieval run: 2026-11-17T02:38:22+00:00.

## 2. Commercial/licensed

Licensed European gas hub forward, spread and execution history; operator performance data if public curves are inadequate. Rights, fees, coverage, historical availability and redistribution are **BLOCKED** until reviewed; no entitlement is implied.

## 3. Private/permissioned only after public feasibility

Optional authorized procurement exposures and storage rights; absent. Do not upload these records, extracts, identifiers or research results to this public repository. Public outputs use only permitted aggregate summaries or synthetic fixtures reviewed for disclosure.

## 4. Research background

- [Boyd and Vandenberghe, Convex Optimization](https://web.stanford.edu/~boyd/cvxbook/) — Verified author-hosted textbook. Background for convex relaxations, not evidence of an economic edge or MILP global optimality. Retrieval run: 2026-11-17T02:38:22+00:00.

**Evidence classification:** portal/methodology existence was checked through current public search/retrieval. No data download, license clearance, point-in-time panel, calibrated model, price reaction, realized return or ROI was verified. Public accessibility does not grant blanket redistribution. Links support only the statements attached to them; theoretical papers do not support the new hypothesis.


**Status: DESIGN WRITTEN. Empirical execution, data-rights clearance, package lock, runtime, backtest, shadow trial and production implementation: BLOCKED pending the documented prerequisites. No research model was run.**

## Navigation

[SPEC](SPEC.md) · [PLAN](PLAN.md) · [TASKS](TASKS.md) · [ROADMAP](ROADMAP.md) · [HANDOFF](HANDOFF.md) · [SOURCES](SOURCES.md) · [AGENT](AGENT.md) · [SKILL](SKILL.md) · [PROMPT](PROMPT.md) · [TOOLING](TOOLING.md) · [WORKFLOW](WORKFLOW.md) · [RUNTIME](RUNTIME.md) · [EVALS](EVALS.md)
