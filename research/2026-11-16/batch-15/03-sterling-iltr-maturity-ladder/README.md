# 03. Sterling ILTR Auction Demand Smoothing

**QMG-20261116-03 · A — Securities finance · Priority 84/100 (editorial judgment)**

**Geography/instruments:** United Kingdom; GBP central-bank secured liquidity. **Difficulty:** High. **Production feasibility:** Public structural simulation feasible; real bidding requires eligible participant authority. **Effort assumption:** One auction researcher and one engineer for 10-14 weeks; treasury and facility access reviews required.

## Problem, decision and economic value

Concentrating reserve demand in one auction can raise clearing-cost and maturity concentration exposure; aggregate results reveal little about competitors' bid curves. **Decision:** Distribute a fixed eligible reserve requirement across future ILTR auctions and collateral sets without assuming a strategic low bid improves the clearing price. Economic value is measured through the declared target and net cost model, not forecast accuracy alone.

**Hypothesis (untested):** Demand smoothing lowers all-in expected funding expense by at least 1 bp relative to a single-auction ladder while preserving liquidity coverage under adverse allocation outcomes.

## Mathematics and decision constraints

```text
min_q sum_(a,c) E[s_ac(Q_a)*q_ac]*T_a/365 + bridge_cost(q); sum_(a,c) q_ac*1{a settles<=t<a matures}>=L_t, sum_a q_ac<=C_c, q_ac>=0
```

a is auction; c collateral set; q is requested GBP cash; s is clearing spread as a function of aggregate demand Q; T tenor days; L reserve requirement; C haircut-adjusted eligible collateral. Bids are bounded by independently estimated willingness-to-pay; no assumed access to competitor bids.

Mathematical conventions: one basis point is 0.0001 of annual rate; dt is the declared year fraction. CVaR_a(L)=min_eta[eta+E[(L-eta)^+]/(1-a)] for loss L and tail level a. Risk/turnover penalties are nonnegative and frozen before holdout; rates, prices, cash and face units must reconcile. All forecasts/expectations are conditional on information available at the decision time. A proposed nonlinear or integer formulation is not asserted convex or globally solved without a solver certificate.

## Data and decision timing

Published BoE operation results, facility rules, publication timestamps, collateral-set spreads and tenors; simulated reserve paths; licensed GBP alternative-funding quotes for later testing. **Grain:** auction x collateral set x release version. **Decision clock:** Use results only after public release; plan by 09:00 Europe/London before an operation using earlier operations and latest approved reserve forecast. Verify each current auction deadline before a live pilot.

Every input carries observed_at, published_at, received_at, available_at=max(published_at, received_at), effective_at, source/version/hash and rights_class. Unknown historical release time is not reconstructed from a present-day file timestamp; use the declared conservative lag or exclude the row. In replay, separate an assumed historical ingestion latency from an actually recorded receive time. Outcomes may arrive later but cannot be features.

## Model comparison and evaluation

- **Credible baseline:** Equal weekly maturities with bids at independently approved maximum willingness-to-pay; compare a single-auction funding plan separately.
- **Suggested candidate:** Shape-constrained aggregate supply-curve estimation plus stochastic ladder optimization.
- **Advanced alternative:** Partially identified robust auction planning over a set of rival-demand curves.
- **Target:** cost of a reserve maturity ladder subject to stressed coverage.
- **Metrics:** GBP funding cost, allocation shortfall, maturity concentration, sensitivity to unobserved demand and bridge usage.
- **Pre-registered stop/go:** GO if >=1 bp net annualized saving versus equal ladder in >=12 held-out operations and no stressed reserve shortfall. STOP if all plausible demand curves imply the same ladder or savings require underbidding actual willingness-to-pay.
- **Critical negative test:** Replace the estimated supply curve with a flat curve: the model must not claim auction-price savings from moving a price-taking bid.

Use chronological development/validation/untouched holdout partitions at the native decision frequency, purging the full target horizon and overlapping event groups. Fit transforms, calibration and policy parameters inside training folds. Cluster uncertainty by the economic event/issuer/season, not by repeated rows; preserve disappeared instruments and failed outcomes. Report all candidate variants and correct selection uncertainty. If effective sample size is inadequate, mark BLOCKED rather than lower the gate. Require baseline and candidate to use the same information, risk, liquidity, fees and execution opportunity.

## Capacity and economics

Illustrative GBP500m reserve need in USD-equivalent ROI; size must be small relative to auction capacity or explicitly model own impact. Operational access, collateral prepositioning and bridge-funding limits bind. Capacity and costs are assumptions until measured at executable sizes. Charge bid/ask, impact, funding, financing/borrow where relevant, settlement costs and the stated operating expense. Double spreads/impact and halve assumed capacity in sensitivity analysis.

**Purely illustrative 24-month ROI; assumptions and arithmetic, not empirical evidence.** USD-equivalent affected exposure $500,000,000; annual net benefit scenarios 0/1/2.5 bps. Value channel: annual all-in funding savings versus a diversified maturity ladder, net of bridge expense. Assume 9 months before benefit starts, 1.25 benefit-years, zero discounting and no terminal value. Two-year all-in engineering/data/review/maintenance cost C=$160,000; this budget is a planning assumption, not a vendor quote. Trading/operating charges are already deducted from scenario benefits; do not deduct them twice.

| Scenario | Annual net benefit before project cost | 24-month benefit B after launch lag | Net ROI (B-C)/C |
|---|---:|---:|---:|
| Downside | $0 | $0 | -100.0% |
| Base | $50,000 | $62,500 | -60.9% |
| Upside | $125,000 | $156,250 | -2.3% |

Break-even annual benefit after launch = $128,000. Full cost is lost if abandoned before benefit; ROI=-100% then. Negative trading/hedge scenarios can be worse than -100%. Utility or avoided-loss scenarios are not guaranteed cash revenue. Budgets and benefits across projects overlap and must not be summed.

## Research value, risk and novelty

**Academic/publication value:** High identification interest, conditional on transparent partial-identification bounds rather than a falsely recovered demand curve. **Key risk:** Aggregate clearing outcomes do not identify individual demand or fill probabilities. Facility calibration changes can invalidate extrapolation; official participation rules take precedence.

**Cumulative novelty check:** Nearest: 2026-11-12/01 stock-loan auction and /02 repo term curve. New decision is demand smoothing across a central-bank auction schedule, with official bidding incentives and aggregate-data identification bounds. Checked against all 35 archived idea READMEs on main; this is a scoped comparison, not certification of originality in academic literature or inaccessible archives.

## Source ladder and truth state

## 1. Public/free first

- [Bank of England ILTR participant guide](https://www.bankofengland.co.uk/markets/using-the-iltr-guide-for-participants) — Facility mechanics and bid guidance. Does not disclose individual competitors' bids or grant facility access. Retrieval run: 2026-11-17T02:38:22+00:00.
- [Bank of England operations results](https://www.bankofengland.co.uk/markets/bank-of-england-market-operations-guide/results-and-usage-data) — Aggregate operation results; extraction, historical release times and usage rights remain implementation gates. Retrieval run: 2026-11-17T02:38:22+00:00.

## 2. Commercial/licensed

Licensed SONIA/GBP funding curves and bond prices; public auction results alone do not establish executable savings. Rights, fees, coverage, historical availability and redistribution are **BLOCKED** until reviewed; no entitlement is implied.

## 3. Private/permissioned only after public feasibility

Permissioned reserve forecasts, approved bid limits and collateral access; absent. Do not upload these records, extracts, identifiers or research results to this public repository. Public outputs use only permitted aggregate summaries or synthetic fixtures reviewed for disclosure.

## 4. Research background

- [Boyd and Vandenberghe, Convex Optimization](https://web.stanford.edu/~boyd/cvxbook/) — Verified author-hosted textbook. Background for convex relaxations, not evidence of an economic edge or MILP global optimality. Retrieval run: 2026-11-17T02:38:22+00:00.

**Evidence classification:** portal/methodology existence was checked through current public search/retrieval. No data download, license clearance, point-in-time panel, calibrated model, price reaction, realized return or ROI was verified. Public accessibility does not grant blanket redistribution. Links support only the statements attached to them; theoretical papers do not support the new hypothesis.


**Status: DESIGN WRITTEN. Empirical execution, data-rights clearance, package lock, runtime, backtest, shadow trial and production implementation: BLOCKED pending the documented prerequisites. No research model was run.**

## Navigation

[SPEC](SPEC.md) · [PLAN](PLAN.md) · [TASKS](TASKS.md) · [ROADMAP](ROADMAP.md) · [HANDOFF](HANDOFF.md) · [SOURCES](SOURCES.md) · [AGENT](AGENT.md) · [SKILL](SKILL.md) · [PROMPT](PROMPT.md) · [TOOLING](TOOLING.md) · [WORKFLOW](WORKFLOW.md) · [RUNTIME](RUNTIME.md) · [EVALS](EVALS.md)
