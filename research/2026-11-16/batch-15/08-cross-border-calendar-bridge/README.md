# 08. Cross-Border Settlement Calendar Bridge Planner

**QMG-20261116-08 · A — Securities finance · Priority 90/100 (editorial judgment)**

**Geography/instruments:** US, euro area and UK financing settlement. **Difficulty:** Medium. **Production feasibility:** High for calendar/calendar-version software; cash amounts and access require a private pilot. **Effort assumption:** One engineer plus part-time treasury researcher for 6-8 weeks.

## Problem, decision and economic value

Cash and securities services may have different holidays or cutoffs, making a financing roll look feasible on a generic business-day calendar when one leg cannot settle. **Decision:** Choose an earlier settlement date and minimal bridge cash for already approved cross-border obligations. Economic value is measured through the declared target and net cost model, not forecast accuracy alone.

**Hypothesis (untested):** A service-specific dated-calendar planner eliminates at least 90% of calendar-caused exceptions and lowers bridge funding cost by 10% versus a fixed two-business-day prefunding rule.

## Mathematics and decision constraints

```text
min_b,t sum_j r_j*b_j*d_j/360 + transfer_j + penalty_j*u_j; cash_balance_(c,t)>=0, settlement_open_(service,t)=1, t_j<=deadline_j, bridge_c<=limit_c
```

j obligation; b bridge cash in local currency; d calendar days; r annual funding rate; u unmet obligation indicator; c currency; t chosen settlement instant. USD ROI converts each realized local-currency cost at decision-time hedged FX rates.

Mathematical conventions: one basis point is 0.0001 of annual rate; dt is the declared year fraction. CVaR_a(L)=min_eta[eta+E[(L-eta)^+]/(1-a)] for loss L and tail level a. Risk/turnover penalties are nonnegative and frozen before holdout; rates, prices, cash and face units must reconcile. All forecasts/expectations are conditional on information available at the decision time. A proposed nonlinear or integer formulation is not asserted convex or globally solved without a solver certificate.

## Data and decision timing

Official service calendars and versioned cutoffs, announced closures/extensions, obligation currency/security legs and value dates, available prefunding routes and firm rates. **Grain:** obligation leg x settlement service x UTC instant. **Decision clock:** Plan at least two local business days before a known holiday, using rules announced by then. Unexpected outages are separate stress scenarios; announced future changes enter only after their publication.

Every input carries observed_at, published_at, received_at, available_at=max(published_at, received_at), effective_at, source/version/hash and rights_class. Unknown historical release time is not reconstructed from a present-day file timestamp; use the declared conservative lag or exclude the row. In replay, separate an assumed historical ingestion latency from an actually recorded receive time. Outcomes may arrive later but cannot be features.

## Model comparison and evaluation

- **Credible baseline:** Prefund every cross-border obligation two generic business days early, with manual holiday review.
- **Suggested candidate:** Time-expanded multi-service cash-flow network.
- **Advanced alternative:** Robust network flow with uncertain service extensions and intraday cash arrival bands.
- **Target:** bridge cash-days and avoidable calendar exceptions.
- **Metrics:** calendar exceptions, cash-days, funding expense, minimum liquidity and cutoff breaches.
- **Pre-registered stop/go:** GO if >=90% calendar exceptions avoided and >=10% net bridge-cost saving on >=24 holiday windows; zero infeasible settlement recommendations. STOP if routing assumptions require unapproved service access.
- **Critical negative test:** Replay US/Europe DST mismatch, Good Friday and a service-specific cutoff extension; the planner must distinguish securities and cash service availability.

Use chronological development/validation/untouched holdout partitions at the native decision frequency, purging the full target horizon and overlapping event groups. Fit transforms, calibration and policy parameters inside training folds. Cluster uncertainty by the economic event/issuer/season, not by repeated rows; preserve disappeared instruments and failed outcomes. Report all candidate variants and correct selection uncertainty. If effective sample size is inadequate, mark BLOCKED rather than lower the gate. Require baseline and candidate to use the same information, risk, liquidity, fees and execution opportunity.

## Capacity and economics

Illustrative $200m annual recurring bridge balances in USD equivalent; same approved obligations, no new FX carry position. Saving bounded by actual overlap days and bridge rates. Capacity and costs are assumptions until measured at executable sizes. Charge bid/ask, impact, funding, financing/borrow where relevant, settlement costs and the stated operating expense. Double spreads/impact and halve assumed capacity in sensitivity analysis.

**Purely illustrative 24-month ROI; assumptions and arithmetic, not empirical evidence.** USD-equivalent affected exposure $200,000,000; annual net benefit scenarios 0/3/6 bps. Value channel: annual bridge-cash-day savings expressed as bps on recurring affected balances, net of transfer fees. Assume 3 months before benefit starts, 1.75 benefit-years, zero discounting and no terminal value. Two-year all-in engineering/data/review/maintenance cost C=$100,000; this budget is a planning assumption, not a vendor quote. Trading/operating charges are already deducted from scenario benefits; do not deduct them twice.

| Scenario | Annual net benefit before project cost | 24-month benefit B after launch lag | Net ROI (B-C)/C |
|---|---:|---:|---:|
| Downside | $0 | $0 | -100.0% |
| Base | $60,000 | $105,000 | 5.0% |
| Upside | $120,000 | $210,000 | 110.0% |

Break-even annual benefit after launch = $57,143. Full cost is lost if abandoned before benefit; ROI=-100% then. Negative trading/hedge scenarios can be worse than -100%. Utility or avoided-loss scenarios are not guaranteed cash revenue. Budgets and benefits across projects overlap and must not be summed.

## Research value, risk and novelty

**Academic/publication value:** Medium: formal temporal service graph and reproducible operational errors; high practical portability. **Key risk:** Future operating-day changes differ between funds and securities services. DST, half-days and local date conventions can introduce 24-hour errors; a public calendar is not a service entitlement.

**Cumulative novelty check:** Nearest: 2026-11-12/03 queueing and /09 currency repo basis. Here fixed obligations are scheduled across deterministically different service calendars; there is no funding-currency arbitrage or queue priority control. Checked against all 35 archived idea READMEs on main; this is a scoped comparison, not certification of originality in academic literature or inaccessible archives.

## Source ladder and truth state

## 1. Public/free first

- [Federal Reserve Financial Services holiday schedules](https://www.frbservices.org/about/holiday-schedules/) — Calendar information; inspect service-specific schedules and effective versions rather than assuming all systems share hours. Retrieval run: 2026-11-17T02:38:22+00:00.
- [Fedwire Securities service hours](https://www.frbservices.org/resources/financial-services/fedwire-securities-resources/fedwire-securities-service-schedule-fedpayments-manager-securities-hours-availability/) — Service operating windows; announced extensions and outages require separately timestamped updates. Retrieval run: 2026-11-17T02:38:22+00:00.
- [ECB TARGET operating schedule](https://www.ecb.europa.eu/paym/target/shared/pdf/TARGET_System_operating_schedule.en.pdf) — Operating-schedule document; effective-date and component-specific interpretation required. Retrieval run: 2026-11-17T02:38:22+00:00.

## 2. Commercial/licensed

Licensed settlement-calendar/corporate-action reference feed if official histories are incomplete. Rights, fees, coverage, historical availability and redistribution are **BLOCKED** until reviewed; no entitlement is implied.

## 3. Private/permissioned only after public feasibility

Approved obligations, service memberships and bridge-funding limits; absent. Do not upload these records, extracts, identifiers or research results to this public repository. Public outputs use only permitted aggregate summaries or synthetic fixtures reviewed for disclosure.

## 4. Research background

- [Boyd and Vandenberghe, Convex Optimization](https://web.stanford.edu/~boyd/cvxbook/) — Verified author-hosted textbook. Background for convex relaxations, not evidence of an economic edge or MILP global optimality. Retrieval run: 2026-11-17T02:38:22+00:00.

**Evidence classification:** portal/methodology existence was checked through current public search/retrieval. No data download, license clearance, point-in-time panel, calibrated model, price reaction, realized return or ROI was verified. Public accessibility does not grant blanket redistribution. Links support only the statements attached to them; theoretical papers do not support the new hypothesis.


**Status: DESIGN WRITTEN. Empirical execution, data-rights clearance, package lock, runtime, backtest, shadow trial and production implementation: BLOCKED pending the documented prerequisites. No research model was run.**

## Navigation

[SPEC](SPEC.md) · [PLAN](PLAN.md) · [TASKS](TASKS.md) · [ROADMAP](ROADMAP.md) · [HANDOFF](HANDOFF.md) · [SOURCES](SOURCES.md) · [AGENT](AGENT.md) · [SKILL](SKILL.md) · [PROMPT](PROMPT.md) · [TOOLING](TOOLING.md) · [WORKFLOW](WORKFLOW.md) · [RUNTIME](RUNTIME.md) · [EVALS](EVALS.md)
