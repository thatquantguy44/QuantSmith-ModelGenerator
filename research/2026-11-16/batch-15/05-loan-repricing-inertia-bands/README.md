# 05. Stock-Loan Repricing Bands with Relationship Friction

**QMG-20261116-05 · A — Securities finance · Priority 91/100 (editorial judgment)**

**Geography/instruments:** United States and developed-Europe equity loans. **Difficulty:** Medium. **Production feasibility:** Synthetic policy replay feasible; empirical uplift blocked by full quote/message history. **Effort assumption:** One researcher and one engineer for 8-12 weeks plus controlled policy review.

## Problem, decision and economic value

Changing a loan fee whenever a benchmark moves creates negotiation expense, borrower exits and operational churn that a fee-only policy misses. **Decision:** Choose a fee-change threshold and batching cadence for existing loans rather than repricing every observed basis-point move. Economic value is measured through the declared target and net cost model, not forecast accuracy alone.

**Hypothesis (untested):** A two-sided repricing band increases net relationship-adjusted revenue by at least 5% versus daily benchmark matching without reducing risk-adjusted balances by more than 2%.

## Mathematics and decision constraints

```text
V(f,m)=max{carry(f,m)+E[V(f,m_next)], max_(f_new)[carry(f_new,m)-K-C_exit(f_new,f,m)+E[V(f_new,m_next)]]}; f_min<=f_new<=f_max, messages_day<=M
```

f is current annualized loan fee; m public/licensed market state; K fixed negotiation/processing cost; C_exit expected lost margin from borrower response; M approved message cap. Carry is fee times marked loan notional times elapsed year fraction, less source costs.

Mathematical conventions: one basis point is 0.0001 of annual rate; dt is the declared year fraction. CVaR_a(L)=min_eta[eta+E[(L-eta)^+]/(1-a)] for loss L and tail level a. Risk/turnover penalties are nonnegative and frozen before holdout; rates, prices, cash and face units must reconcile. All forecasts/expectations are conditional on information available at the decision time. A proposed nonlinear or integer formulation is not asserted convex or globally solved without a solver certificate.

## Data and decision timing

Existing-loan fee changes, proposal/acknowledgment timestamps, rejected changes, borrower exits, balances, fee benchmarks and support-message labor. A contributed fee panel alone cannot identify retention elasticity. **Grain:** loan x repricing proposal/response event. **Decision clock:** Review at 10:00 local market time with benchmark releases and acknowledgments available by 09:55. Use an effective fee only after both contractual acceptance and booking; no retroactive filled proposals.

Every input carries observed_at, published_at, received_at, available_at=max(published_at, received_at), effective_at, source/version/hash and rights_class. Unknown historical release time is not reconstructed from a present-day file timestamp; use the declared conservative lag or exclude the row. In replay, separate an assumed historical ingestion latency from an actually recorded receive time. Outcomes may arrive later but cannot be features.

## Model comparison and evaluation

- **Credible baseline:** Match yesterday's observable benchmark daily, with contractual limits; also compare a fixed 10-bp band.
- **Suggested candidate:** Impulse-control dynamic program with survival-calibrated borrower exits.
- **Advanced alternative:** Hierarchical Bayesian partially observed control with conservative policy evaluation.
- **Target:** incremental net fee dollars minus message labor and attrition loss.
- **Metrics:** net margin, retention-adjusted balance, messages per loan, calibration, implementation shortfall and subgroup concentration.
- **Pre-registered stop/go:** GO if >=5% net revenue improvement with bootstrap lower bound >0 and balance loss <=2% in a pre-registered eligible cohort; no subgroup >5% deterioration. STOP if benefit relies on unobserved rejected requests or violates agreed repricing rights.
- **Critical negative test:** Set negotiation and exit costs to zero: the optimal inaction band should collapse under an otherwise frictionless model; rejected proposals must never become realized fees.

Use chronological development/validation/untouched holdout partitions at the native decision frequency, purging the full target horizon and overlapping event groups. Fit transforms, calibration and policy parameters inside training folds. Cluster uncertainty by the economic event/issuer/season, not by repeated rows; preserve disappeared instruments and failed outcomes. Report all candidate variants and correct selection uncertainty. If effective sample size is inadequate, mark BLOCKED rather than lower the gate. Require baseline and candidate to use the same information, risk, liquidity, fees and execution opportunity.

## Capacity and economics

Illustrative $400m existing balances; not a new trading strategy. Control concentration and fee elasticity; bps benefit must be net of exits, source revenue sharing and labor. Capacity and costs are assumptions until measured at executable sizes. Charge bid/ask, impact, funding, financing/borrow where relevant, settlement costs and the stated operating expense. Double spreads/impact and halve assumed capacity in sensitivity analysis.

**Purely illustrative 24-month ROI; assumptions and arithmetic, not empirical evidence.** USD-equivalent affected exposure $400,000,000; annual net benefit scenarios 0/2/4 bps. Value channel: annual net repricing benefit after borrower attrition, processing labor and revenue share. Assume 6 months before benefit starts, 1.5 benefit-years, zero discounting and no terminal value. Two-year all-in engineering/data/review/maintenance cost C=$130,000; this budget is a planning assumption, not a vendor quote. Trading/operating charges are already deducted from scenario benefits; do not deduct them twice.

| Scenario | Annual net benefit before project cost | 24-month benefit B after launch lag | Net ROI (B-C)/C |
|---|---:|---:|---:|
| Downside | $0 | $0 | -100.0% |
| Base | $80,000 | $120,000 | -7.7% |
| Upside | $160,000 | $240,000 | 84.6% |

Break-even annual benefit after launch = $86,667. Full cost is lost if abandoned before benefit; ROI=-100% then. Negative trading/hedge scenarios can be worse than -100%. Utility or avoided-loss scenarios are not guaranteed cash revenue. Budgets and benefits across projects overlap and must not be summed.

## Research value, risk and novelty

**Academic/publication value:** Medium-high: measurable market-design frictions and interpretable control boundaries. **Key risk:** Repricing is endogenous to scarcity and relationship quality. Off-policy evaluation cannot fix zero action overlap; randomized eligible shadow suggestions need business approval.

**Cumulative novelty check:** Nearest: 2026-11-12/13 execution shortfall and 2026-11-13/08 sample selection. This optimizes a repeated fee-adjustment policy with switching and attrition costs, rather than attributing leakage or estimating a fee surface. Checked against all 35 archived idea READMEs on main; this is a scoped comparison, not certification of originality in academic literature or inaccessible archives.

## Source ladder and truth state

## 1. Public/free first

- [SEC Form N-PORT data sets](https://www.sec.gov/data-research/sec-markets-data/form-n-port-data-sets) — Public filing extracts; reporting period is not public availability. No intraday inventory or client withdrawal records. Retrieval run: 2026-11-17T02:38:22+00:00.
- [New York Fed reference-rate methodology](https://www.newyorkfed.org/markets/reference-rates/additional-information-about-reference-rates) — Official methodology, revision and contingency rules; portal checked, underlying transaction records are not public here. Retrieval run: 2026-11-17T02:38:22+00:00.

## 2. Commercial/licensed

Licensed securities-lending fee benchmarks under institution-specific contracts; no verified entitlement or extracts obtained. Rights, fees, coverage, historical availability and redistribution are **BLOCKED** until reviewed; no entitlement is implied.

## 3. Private/permissioned only after public feasibility

Complete repricing proposals, accepts/rejects, relationship balances and labor logs; absent. Do not upload these records, extracts, identifiers or research results to this public repository. Public outputs use only permitted aggregate summaries or synthetic fixtures reviewed for disclosure.

## 4. Research background

- [Boyd and Vandenberghe, Convex Optimization](https://web.stanford.edu/~boyd/cvxbook/) — Verified author-hosted textbook. Background for convex relaxations, not evidence of an economic edge or MILP global optimality. Retrieval run: 2026-11-17T02:38:22+00:00.

**Evidence classification:** portal/methodology existence was checked through current public search/retrieval. No data download, license clearance, point-in-time panel, calibrated model, price reaction, realized return or ROI was verified. Public accessibility does not grant blanket redistribution. Links support only the statements attached to them; theoretical papers do not support the new hypothesis.


**Status: DESIGN WRITTEN. Empirical execution, data-rights clearance, package lock, runtime, backtest, shadow trial and production implementation: BLOCKED pending the documented prerequisites. No research model was run.**

## Navigation

[SPEC](SPEC.md) · [PLAN](PLAN.md) · [TASKS](TASKS.md) · [ROADMAP](ROADMAP.md) · [HANDOFF](HANDOFF.md) · [SOURCES](SOURCES.md) · [AGENT](AGENT.md) · [SKILL](SKILL.md) · [PROMPT](PROMPT.md) · [TOOLING](TOOLING.md) · [WORKFLOW](WORKFLOW.md) · [RUNTIME](RUNTIME.md) · [EVALS](EVALS.md)
