# 10. Securities-Loan Dust-Lot Consolidation

**QMG-20261116-10 · A — Securities finance · Priority 88/100 (editorial judgment)**

**Geography/instruments:** US and developed-market equity lending. **Difficulty:** Medium. **Production feasibility:** High synthetic integer-allocation prototype; business savings need authorized processing costs. **Effort assumption:** One optimization engineer and part-time lending researcher for 6-8 weeks.

## Problem, decision and economic value

Many tiny loan lots can earn less than their servicing and settlement cost even when aggregate inventory and demand are unchanged. **Decision:** Consolidate or close eligible small lots within the same owner/borrower/legal permissions while preserving economic exposure and service constraints. Economic value is measured through the declared target and net cost model, not forecast accuracy alone.

**Hypothesis (untested):** Integer cost-aware lot consolidation cuts recurring servicing expense by at least 20% relative to pro-rata allocation without reducing net lending revenue by more than 1%.

## Mathematics and decision constraints

```text
max_(x,z) sum_(o,b,i) fee_obi*x_obi*dt - k_obi*z_obi - move_cost; lot_i*z_obi<=x_obi<=M_obi*z_obi, sum_b x_obi<=I_oi, sum_o x_obi=D_bi, z binary
```

o owner, b borrower, i security; x loan quantity; z active lot; fee net per-unit revenue; k recurring ticket cost; lot minimum economic/settlement size; I inventory; D approved demand; M individual legal capacity. Existing owner allocations may be immutable unless consent permits changes.

Mathematical conventions: one basis point is 0.0001 of annual rate; dt is the declared year fraction. CVaR_a(L)=min_eta[eta+E[(L-eta)^+]/(1-a)] for loss L and tail level a. Risk/turnover penalties are nonnegative and frozen before holdout; rates, prices, cash and face units must reconcile. All forecasts/expectations are conditional on information available at the decision time. A proposed nonlinear or integer formulation is not asserted convex or globally solved without a solver certificate.

## Data and decision timing

Synthetic owner/borrower inventories, approved minimum lots, source shares, per-ticket servicing fees, loan quantities, movement cost and owner allocation rules. No real owner or borrower data are committed. **Grain:** owner x borrower x security loan lot x service day. **Decision clock:** Solve after confirmed end-of-day books and before next-day instruction cutoff; only booked demand and valid consent known at solve time enter. Settled movements are later outcomes.

Every input carries observed_at, published_at, received_at, available_at=max(published_at, received_at), effective_at, source/version/hash and rights_class. Unknown historical release time is not reconstructed from a present-day file timestamp; use the declared conservative lag or exclude the row. In replay, separate an assumed historical ingestion latency from an actually recorded receive time. Outcomes may arrive later but cannot be features.

## Model comparison and evaluation

- **Credible baseline:** Pro-rata eligible allocation across owners, subject to existing concentration caps.
- **Suggested candidate:** Fixed-charge transportation MILP.
- **Advanced alternative:** Multi-period lot consolidation with persistence penalties and uncertain demand bands.
- **Target:** active-ticket count and net servicing-adjusted margin.
- **Metrics:** servicing cost, active lots, net revenue, owner fairness constraints, turnover and time to solve.
- **Pre-registered stop/go:** GO if >=20% servicing-cost saving and <=1% net revenue loss, zero owner-rights violations and payback within 12 months on measured cost inputs. STOP if gains disappear after movement fees or permitted allocations are fixed.
- **Critical negative test:** Set per-ticket cost to zero: consolidation must not invent savings; introduce an owner-specific nontransferability flag and verify its lot remains untouched.

Use chronological development/validation/untouched holdout partitions at the native decision frequency, purging the full target horizon and overlapping event groups. Fit transforms, calibration and policy parameters inside training folds. Cluster uncertainty by the economic event/issuer/season, not by repeated rows; preserve disappeared instruments and failed outcomes. Report all candidate variants and correct selection uncertainty. If effective sample size is inadequate, mark BLOCKED rather than lower the gate. Require baseline and candidate to use the same information, risk, liquidity, fees and execution opportunity.

## Capacity and economics

Illustrative 50,000 serviced lots per year; no market ADV capacity claim. Benefits limited by actual removable lots and movement/consent cost, not gross notional. Capacity and costs are assumptions until measured at executable sizes. Charge bid/ask, impact, funding, financing/borrow where relevant, settlement costs and the stated operating expense. Double spreads/impact and halve assumed capacity in sensitivity analysis.

**Purely illustrative 24-month ROI; assumptions and arithmetic, not empirical evidence.** 50,000 annual units x $3/unit x effectiveness 0/0.5/1. Value channel: annual eligible ticket-service savings: 50,000 lots times $3 saved times realized consolidation effectiveness, after movement fees. Assume 3 months before benefit starts, 1.75 benefit-years, zero discounting and no terminal value. Two-year all-in engineering/data/review/maintenance cost C=$110,000; this budget is a planning assumption, not a vendor quote. Trading/operating charges are already deducted from scenario benefits; do not deduct them twice.

| Scenario | Annual net benefit before project cost | 24-month benefit B after launch lag | Net ROI (B-C)/C |
|---|---:|---:|---:|
| Downside | $0 | $0 | -100.0% |
| Base | $75,000 | $131,250 | 19.3% |
| Upside | $150,000 | $262,500 | 138.6% |

Break-even annual benefit after launch = $62,857. Full cost is lost if abandoned before benefit; ROI=-100% then. Negative trading/hedge scenarios can be worse than -100%. Utility or avoided-loss scenarios are not guaranteed cash revenue. Budgets and benefits across projects overlap and must not be summed.

## Research value, risk and novelty

**Academic/publication value:** Medium: fixed-charge inventory allocation with fair attribution; production engineering likely more valuable than model novelty. **Key risk:** Tax lots, revenue attribution, beneficial-owner fairness and contract permissions can prohibit economically appealing consolidation. Unit-cost assumptions often dominate the result.

**Cumulative novelty check:** Nearest: 2026-11-12/01 auction allocation. Demand and fees are fixed here; the objective is reducing fixed service costs subject to lot granularity and ownership constraints, with no demand discovery or auction mechanism. Checked against all 35 archived idea READMEs on main; this is a scoped comparison, not certification of originality in academic literature or inaccessible archives.

## Source ladder and truth state

## 1. Public/free first

- [SEC Form N-PORT data sets](https://www.sec.gov/data-research/sec-markets-data/form-n-port-data-sets) — Public filing extracts; reporting period is not public availability. No intraday inventory or client withdrawal records. Retrieval run: 2026-11-17T02:38:22+00:00.
- [DTCC repo service description](https://www.dtcc.com/clearing-and-settlement-services/ficc-gov/repo) — Service context only; no claim that proposed compression is a supported product or legally permissible for every trade. Retrieval run: 2026-11-17T02:38:22+00:00.

## 2. Commercial/licensed

Licensed processing tariff/reference data where needed; no price history required for initial synthetic optimization. Rights, fees, coverage, historical availability and redistribution are **BLOCKED** until reviewed; no entitlement is implied.

## 3. Private/permissioned only after public feasibility

Authorized ticket-cost and owner allocation permissions; absent. Do not upload these records, extracts, identifiers or research results to this public repository. Public outputs use only permitted aggregate summaries or synthetic fixtures reviewed for disclosure.

## 4. Research background

- [Boyd and Vandenberghe, Convex Optimization](https://web.stanford.edu/~boyd/cvxbook/) — Verified author-hosted textbook. Background for convex relaxations, not evidence of an economic edge or MILP global optimality. Retrieval run: 2026-11-17T02:38:22+00:00.

**Evidence classification:** portal/methodology existence was checked through current public search/retrieval. No data download, license clearance, point-in-time panel, calibrated model, price reaction, realized return or ROI was verified. Public accessibility does not grant blanket redistribution. Links support only the statements attached to them; theoretical papers do not support the new hypothesis.


**Status: DESIGN WRITTEN. Empirical execution, data-rights clearance, package lock, runtime, backtest, shadow trial and production implementation: BLOCKED pending the documented prerequisites. No research model was run.**

## Navigation

[SPEC](SPEC.md) · [PLAN](PLAN.md) · [TASKS](TASKS.md) · [ROADMAP](ROADMAP.md) · [HANDOFF](HANDOFF.md) · [SOURCES](SOURCES.md) · [AGENT](AGENT.md) · [SKILL](SKILL.md) · [PROMPT](PROMPT.md) · [TOOLING](TOOLING.md) · [WORKFLOW](WORKFLOW.md) · [RUNTIME](RUNTIME.md) · [EVALS](EVALS.md)
