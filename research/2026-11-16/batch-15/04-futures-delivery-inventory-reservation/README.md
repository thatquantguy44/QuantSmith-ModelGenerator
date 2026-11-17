# 04. Treasury Futures Delivery Inventory Reservation

**QMG-20261116-04 · A — Securities finance · Priority 86/100 (editorial judgment)**

**Geography/instruments:** United States; Treasury futures deliverable baskets and securities loans. **Difficulty:** High. **Production feasibility:** Analytical prototype feasible; security-level lending and futures prices require licensed/permissioned inputs. **Effort assumption:** One derivatives researcher and one engineer for 12-16 weeks.

## Problem, decision and economic value

Lending a deliverable Treasury can forfeit a valuable delivery choice or force expensive replacement near a futures delivery window. **Decision:** Reserve eligible inventory for an existing futures short versus lending it, charging the marginal delivery-option opportunity cost. Economic value is measured through the declared target and net cost model, not forecast accuracy alone.

**Hypothesis (untested):** A delivery-option reserve beats a fixed percentage holdback by at least 2 bps of annualized affected inventory value, after replacement, lending and hedge costs.

## Mathematics and decision constraints

```text
max_l E[sum_i fee_i*l_i*dt + V_delivery(I-l,F,P)] - replacement(l); 0<=l_i<=I_i, sum_i d_i=N_contracts, face_per_contract*d_i<=I_i-l_i, d_i integer>=0, stress_DV01<=limit
```

I and l are face inventory and lent quantity; CF conversion factors enter invoice_i=face_per_contract*(CF_i*F+AI_i)/100; d_i integer delivery contracts assigned to CUSIP i; N_contracts existing delivery obligation; F futures price per 100 face; AI accrued interest per 100 face; P cash prices; V_delivery optimal invoice less cash opportunity value under delivery rules. Fee carry uses the actual marked value and year fraction; inventory eligibility and delivery date are hard constraints.

Mathematical conventions: one basis point is 0.0001 of annual rate; dt is the declared year fraction. CVaR_a(L)=min_eta[eta+E[(L-eta)^+]/(1-a)] for loss L and tail level a. Risk/turnover penalties are nonnegative and frozen before holdout; rates, prices, cash and face units must reconcile. All forecasts/expectations are conditional on information available at the decision time. A proposed nonlinear or integer formulation is not asserted convex or globally solved without a solver certificate.

## Data and decision timing

Published conversion factors and contract rules; futures and cash bid/ask, repo fees, loan terms, delivery notices and hedge positions. Public basket tables are insufficient for option valuation. **Grain:** CUSIP x futures contract x observation timestamp. **Decision clock:** Reserve at 15:00 America/Chicago using quotes available by 14:55 and current contract basket version; subsequent delivery notices are outcomes, never predictive features.

Every input carries observed_at, published_at, received_at, available_at=max(published_at, received_at), effective_at, source/version/hash and rights_class. Unknown historical release time is not reconstructed from a present-day file timestamp; use the declared conservative lag or exclude the row. In replay, separate an assumed historical ingestion latency from an actually recorded receive time. Outcomes may arrive later but cannot be features.

## Model comparison and evaluation

- **Credible baseline:** Hold back 10% of eligible basket inventory and allocate remaining loans using current fees.
- **Suggested candidate:** Scenario dynamic programming for marginal delivery-option value.
- **Advanced alternative:** Least-squares Monte Carlo with joint cash/futures/repo scenarios and integer delivery sizing.
- **Target:** net lending revenue plus delivery economics for a fixed pre-existing futures obligation.
- **Metrics:** total net economics, forced replacement, delivery feasibility, hedge error and option-value stability.
- **Pre-registered stop/go:** GO if >=2 annualized bps saving over fixed holdback across >=8 delivery cycles, no missed delivery and positive benefit at twice observed transaction costs. STOP if gains depend on hindsight cheapest-to-deliver identity.
- **Critical negative test:** Freeze the basket to a single security: option-selection value must vanish; change conversion factor units and require invoice identity failure rather than silent rescaling.

Use chronological development/validation/untouched holdout partitions at the native decision frequency, purging the full target horizon and overlapping event groups. Fit transforms, calibration and policy parameters inside training folds. Cluster uncertainty by the economic event/issuer/season, not by repeated rows; preserve disappeared instruments and failed outcomes. Report all candidate variants and correct selection uncertainty. If effective sample size is inadequate, mark BLOCKED rather than lower the gate. Require baseline and candidate to use the same information, risk, liquidity, fees and execution opportunity.

## Capacity and economics

Illustrative $250m affected deliverable inventory. Limited by futures obligation size and deliverable-lot depth; do not take a new directional basis trade merely to generate lending revenue. Capacity and costs are assumptions until measured at executable sizes. Charge bid/ask, impact, funding, financing/borrow where relevant, settlement costs and the stated operating expense. Double spreads/impact and halve assumed capacity in sensitivity analysis.

**Purely illustrative 24-month ROI; assumptions and arithmetic, not empirical evidence.** USD-equivalent affected exposure $250,000,000; annual net benefit scenarios 0/3/6 bps. Value channel: annual incremental total economics on existing delivery inventory after all hedge and replacement charges. Assume 9 months before benefit starts, 1.25 benefit-years, zero discounting and no terminal value. Two-year all-in engineering/data/review/maintenance cost C=$190,000; this budget is a planning assumption, not a vendor quote. Trading/operating charges are already deducted from scenario benefits; do not deduct them twice.

| Scenario | Annual net benefit before project cost | 24-month benefit B after launch lag | Net ROI (B-C)/C |
|---|---:|---:|---:|
| Downside | $0 | $0 | -100.0% |
| Base | $75,000 | $93,750 | -50.7% |
| Upside | $150,000 | $187,500 | -1.3% |

Break-even annual benefit after launch = $152,000. Full cost is lost if abandoned before benefit; ROI=-100% then. Negative trading/hedge scenarios can be worse than -100%. Utility or avoided-loss scenarios are not guaranteed cash revenue. Budgets and benefits across projects overlap and must not be summed.

## Research value, risk and novelty

**Academic/publication value:** High: interaction of delivery options and lending availability; empirical claim requires licensed synchronized markets. **Key risk:** Endogenous cheapest-to-deliver switches, delivery timing rules and fee cancellation terms matter; mark-to-model delivery value is not realized cash profit.

**Cumulative novelty check:** Nearest: 2026-11-12/07 specials RV. Here the action is inventory reservation for an existing contractual delivery obligation, not cross-CUSIP scarcity convergence trading. Checked against all 35 archived idea READMEs on main; this is a scoped comparison, not certification of originality in academic literature or inaccessible archives.

## Source ladder and truth state

## 1. Public/free first

- [CME Treasury conversion-factor tables](https://www.cmegroup.com/trading/interest-rates/us-treasury-futures-conversion-factor-lookup-tables.html) — Contract delivery conversion factors; executable futures, cash and repo price history is a separate licensed requirement. Retrieval run: 2026-11-17T02:38:22+00:00.
- [New York Fed reference-rate methodology](https://www.newyorkfed.org/markets/reference-rates/additional-information-about-reference-rates) — Official methodology, revision and contingency rules; portal checked, underlying transaction records are not public here. Retrieval run: 2026-11-17T02:38:22+00:00.

## 2. Commercial/licensed

Licensed synchronized cash Treasury, futures and security-specific financing prices. Rights, fees, coverage, historical availability and redistribution are **BLOCKED** until reviewed; no entitlement is implied.

## 3. Private/permissioned only after public feasibility

Existing futures obligations, inventory and loan restrictions; absent and excluded from public artifacts. Do not upload these records, extracts, identifiers or research results to this public repository. Public outputs use only permitted aggregate summaries or synthetic fixtures reviewed for disclosure.

## 4. Research background

- [Boyd and Vandenberghe, Convex Optimization](https://web.stanford.edu/~boyd/cvxbook/) — Verified author-hosted textbook. Background for convex relaxations, not evidence of an economic edge or MILP global optimality. Retrieval run: 2026-11-17T02:38:22+00:00.

**Evidence classification:** portal/methodology existence was checked through current public search/retrieval. No data download, license clearance, point-in-time panel, calibrated model, price reaction, realized return or ROI was verified. Public accessibility does not grant blanket redistribution. Links support only the statements attached to them; theoretical papers do not support the new hypothesis.


**Status: DESIGN WRITTEN. Empirical execution, data-rights clearance, package lock, runtime, backtest, shadow trial and production implementation: BLOCKED pending the documented prerequisites. No research model was run.**

## Navigation

[SPEC](SPEC.md) · [PLAN](PLAN.md) · [TASKS](TASKS.md) · [ROADMAP](ROADMAP.md) · [HANDOFF](HANDOFF.md) · [SOURCES](SOURCES.md) · [AGENT](AGENT.md) · [SKILL](SKILL.md) · [PROMPT](PROMPT.md) · [TOOLING](TOOLING.md) · [WORKFLOW](WORKFLOW.md) · [RUNTIME](RUNTIME.md) · [EVALS](EVALS.md)
