# 07. Owner Co-Withdrawal Limits for Lendable Inventory

**QMG-20261116-07 · A — Securities finance · Priority 85/100 (editorial judgment)**

**Geography/instruments:** US and European agency lending mandates. **Difficulty:** High. **Production feasibility:** Public fund aggregates can motivate scenarios; production requires private owner availability history. **Effort assumption:** One risk researcher and one engineer for 12 weeks, conditional on a sufficiently long approved panel.

## Problem, decision and economic value

Inventory supplied by many owners may still disappear together when mandates share flows or rebalance dates, making head-count diversification misleading. **Decision:** Cap loans supported by correlated sources and keep replacement options against simultaneous owner withdrawals. Economic value is measured through the declared target and net cost model, not forecast accuracy alone.

**Hypothesis (untested):** Tail co-withdrawal limits reduce 99th-percentile replacement cost by at least 15% versus owner-notional caps without sacrificing more than 2% normal lending revenue.

## Mathematics and decision constraints

```text
max_x sum_o mu_o*x_o - lambda*CVaR_99(sum_o (x_o-S_o)^+*c_o); sum_o x_o<=D, 0<=x_o<=I_o, x_o<=k_o*I_total
```

o owner; x committed loan support; I available inventory; S scenario remaining supply; c replacement spread-cost converted to dollars; D demand; mu net expected fee per quantity; k owner concentration cap; lambda tail-cost aversion.

Mathematical conventions: one basis point is 0.0001 of annual rate; dt is the declared year fraction. CVaR_a(L)=min_eta[eta+E[(L-eta)^+]/(1-a)] for loss L and tail level a. Risk/turnover penalties are nonnegative and frozen before holdout; rates, prices, cash and face units must reconcile. All forecasts/expectations are conditional on information available at the decision time. A proposed nonlinear or integer formulation is not asserted convex or globally solved without a solver certificate.

## Data and decision timing

Permissioned daily available/withdrawn quantities by owner and security, mandate inception/termination, owner-group lineage, public N-PORT filings and known rebalance calendars. Public monthly/quarterly holdings are lagged aggregate context only. **Grain:** owner x security x dated available-inventory snapshot. **Decision clock:** Set next-day inventory limits after local close using confirmed availability received by cutoff; public fund holdings enter at filing acceptance, not portfolio as-of date. Never condition on the owner's future sale or recall notice.

Every input carries observed_at, published_at, received_at, available_at=max(published_at, received_at), effective_at, source/version/hash and rights_class. Unknown historical release time is not reconstructed from a present-day file timestamp; use the declared conservative lag or exclude the row. In replay, separate an assumed historical ingestion latency from an actually recorded receive time. Outcomes may arrive later but cannot be features.

## Model comparison and evaluation

- **Credible baseline:** Static 10% owner concentration cap with independent withdrawal probabilities.
- **Suggested candidate:** Hierarchical common-factor withdrawal model and CVaR allocation.
- **Advanced alternative:** Distributionally robust copula stress allocation with mandate-group shocks.
- **Target:** joint inventory-shortfall distribution and net cost of an allocation limit.
- **Metrics:** tail replacement cost, simultaneous-shortfall calibration, revenue retained, stress coverage and concentration.
- **Pre-registered stop/go:** GO if 99th-percentile cost improves >=15%, normal net revenue loss <=2%, and at least 3 distinct withdrawal episodes are held out; STOP if dependence is unidentified or fewer than 24 months of owner histories exist.
- **Critical negative test:** Duplicate an owner under two IDs: effective diversification must not improve; simulate perfect co-withdrawal and verify the model does not report independent-source protection.

Use chronological development/validation/untouched holdout partitions at the native decision frequency, purging the full target horizon and overlapping event groups. Fit transforms, calibration and policy parameters inside training folds. Cluster uncertainty by the economic event/issuer/season, not by repeated rows; preserve disappeared instruments and failed outcomes. Report all candidate variants and correct selection uncertainty. If effective sample size is inadequate, mark BLOCKED rather than lower the gate. Require baseline and candidate to use the same information, risk, liquidity, fees and execution opportunity.

## Capacity and economics

Illustrative $500m supported inventory; direct benefits limited to replacement-cost savings and retained fee revenue. Extreme withdrawals may have no feasible replacement regardless of model. Capacity and costs are assumptions until measured at executable sizes. Charge bid/ask, impact, funding, financing/borrow where relevant, settlement costs and the stated operating expense. Double spreads/impact and halve assumed capacity in sensitivity analysis.

**Purely illustrative 24-month ROI; assumptions and arithmetic, not empirical evidence.** USD-equivalent affected exposure $500,000,000; annual net benefit scenarios 0/1/3 bps. Value channel: annual net replacement-cost reduction after normal-revenue sacrifice and hedge costs. Assume 9 months before benefit starts, 1.25 benefit-years, zero discounting and no terminal value. Two-year all-in engineering/data/review/maintenance cost C=$170,000; this budget is a planning assumption, not a vendor quote. Trading/operating charges are already deducted from scenario benefits; do not deduct them twice.

| Scenario | Annual net benefit before project cost | 24-month benefit B after launch lag | Net ROI (B-C)/C |
|---|---:|---:|---:|
| Downside | $0 | $0 | -100.0% |
| Base | $50,000 | $62,500 | -63.2% |
| Upside | $150,000 | $187,500 | 10.3% |

Break-even annual benefit after launch = $136,000. Full cost is lost if abandoned before benefit; ROI=-100% then. Negative trading/hedge scenarios can be worse than -100%. Utility or avoided-loss scenarios are not guaranteed cash revenue. Budgets and benefits across projects overlap and must not be summed.

## Research value, risk and novelty

**Academic/publication value:** High if dependence is identifiable; otherwise honest bounds on inventory diversification are useful internal research. **Key risk:** Mandate closure is not an iid recall; inactive and terminated owners must remain in the sample. Co-movement can be driven by security demand rather than shared owner behavior.

**Cumulative novelty check:** Nearest: 2026-11-12/08 recall exercise. This fixes individual recall behavior and optimizes source concentration against joint mandate withdrawal, rather than timing a recall or predicting its exercise boundary. Checked against all 35 archived idea READMEs on main; this is a scoped comparison, not certification of originality in academic literature or inaccessible archives.

## Source ladder and truth state

## 1. Public/free first

- [SEC Form N-PORT data sets](https://www.sec.gov/data-research/sec-markets-data/form-n-port-data-sets) — Public filing extracts; reporting period is not public availability. No intraday inventory or client withdrawal records. Retrieval run: 2026-11-17T02:38:22+00:00.

## 2. Commercial/licensed

Licensed owner/fund classification and securities-lending price history, subject to rights. Rights, fees, coverage, historical availability and redistribution are **BLOCKED** until reviewed; no entitlement is implied.

## 3. Private/permissioned only after public feasibility

Owner-level availability and mandate lineage, with explicit consent and minimum-access controls; absent. Do not upload these records, extracts, identifiers or research results to this public repository. Public outputs use only permitted aggregate summaries or synthetic fixtures reviewed for disclosure.

## 4. Research background

- [Boyd and Vandenberghe, Convex Optimization](https://web.stanford.edu/~boyd/cvxbook/) — Verified author-hosted textbook. Background for convex relaxations, not evidence of an economic edge or MILP global optimality. Retrieval run: 2026-11-17T02:38:22+00:00.

**Evidence classification:** portal/methodology existence was checked through current public search/retrieval. No data download, license clearance, point-in-time panel, calibrated model, price reaction, realized return or ROI was verified. Public accessibility does not grant blanket redistribution. Links support only the statements attached to them; theoretical papers do not support the new hypothesis.


**Status: DESIGN WRITTEN. Empirical execution, data-rights clearance, package lock, runtime, backtest, shadow trial and production implementation: BLOCKED pending the documented prerequisites. No research model was run.**

## Navigation

[SPEC](SPEC.md) · [PLAN](PLAN.md) · [TASKS](TASKS.md) · [ROADMAP](ROADMAP.md) · [HANDOFF](HANDOFF.md) · [SOURCES](SOURCES.md) · [AGENT](AGENT.md) · [SKILL](SKILL.md) · [PROMPT](PROMPT.md) · [TOOLING](TOOLING.md) · [WORKFLOW](WORKFLOW.md) · [RUNTIME](RUNTIME.md) · [EVALS](EVALS.md)
