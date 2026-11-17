# 02. ECB Collateral Eligibility-Cliff Prepositioning

**QMG-20261116-02 · A — Securities finance · Priority 92/100 (editorial judgment)**

**Geography/instruments:** Euro area; EUR marketable collateral. **Difficulty:** Medium. **Production feasibility:** High for public change surveillance; replacement execution needs eligible balances and firm quotes. **Effort assumption:** One researcher plus one data engineer for 6-10 weeks before a private execution pilot.

## Problem, decision and economic value

A known future maturity or announced eligibility change can create a clustered replacement demand that static cheapest-to-deliver allocation ignores. **Decision:** Preposition replacement assets before an announced effective date while charging carry, haircut and transfer costs. Economic value is measured through the declared target and net cost model, not forecast accuracy alone.

**Hypothesis (untested):** A versioned effective-date planner lowers replacement expense by at least 2 annualized basis points on affected balances versus replacing at the deadline, with no use of information before announcement.

## Mathematics and decision constraints

```text
min_y sum_(i,t) (carry_it*y_it + transfer_it*abs(y_it-y_i,t-1)) + lambda*CVaR_95(shortfall); sum_i P_it*(1-h_it)*y_it>=L_t, 0<=y_it<=I_it, y_it=0 if E_it=0
```

i indexes assets; t future business dates; y is pledged quantity; P is as-of scenario price; h is effective haircut; L required secured value; I eligible inventory; E is eligibility known or announced at decision time; lambda prices shortfall risk.

Mathematical conventions: one basis point is 0.0001 of annual rate; dt is the declared year fraction. CVaR_a(L)=min_eta[eta+E[(L-eta)^+]/(1-a)] for loss L and tail level a. Risk/turnover penalties are nonnegative and frozen before holdout; rates, prices, cash and face units must reconcile. All forecasts/expectations are conditional on information available at the decision time. A proposed nonlinear or integer formulation is not asserted convex or globally solved without a solver certificate.

## Data and decision timing

ECB full/delta eligibility files, announcement timestamps, effective dates, maturity, haircuts, issuer mapping, replacement prices and settlement windows. Do not infer a future delisting from a later archive snapshot. **Grain:** ISIN x release version x effective date. **Decision clock:** Evaluate after verified ECB publication and ingestion, with a minimum 30-minute operational latency; any action is next eligible settlement window. Historical daily snapshots without timestamp proof are usable only with a conservative next-business-day decision lag.

Every input carries observed_at, published_at, received_at, available_at=max(published_at, received_at), effective_at, source/version/hash and rights_class. Unknown historical release time is not reconstructed from a present-day file timestamp; use the declared conservative lag or exclude the row. In replay, separate an assumed historical ingestion latency from an actually recorded receive time. Outcomes may arrive later but cannot be features.

## Model comparison and evaluation

- **Credible baseline:** Replace only at maturity or first effective ineligibility date using cheapest currently eligible asset.
- **Suggested candidate:** Rolling-horizon linear allocation using announced eligibility transitions.
- **Advanced alternative:** Distributionally robust prepositioning under uncertain unannounced eligibility loss.
- **Target:** replacement implementation cost and eligible-value shortfall.
- **Metrics:** net carry/transfer expense, shortfall, false early replacements, turnover and issuer concentration.
- **Pre-registered stop/go:** GO if cost saving >=2 annualized bps on affected balances and zero eligibility violations across >=20 independent transition clusters; worst stress shortfall no larger than baseline. STOP if timestamp-safe sample is inadequate or cost rises under doubled bid/ask.
- **Critical negative test:** Move an announcement after the decision timestamp: all corresponding anticipatory trades must disappear; maturity may remain predictable from previously published terms.

Use chronological development/validation/untouched holdout partitions at the native decision frequency, purging the full target horizon and overlapping event groups. Fit transforms, calibration and policy parameters inside training folds. Cluster uncertainty by the economic event/issuer/season, not by repeated rows; preserve disappeared instruments and failed outcomes. Report all candidate variants and correct selection uncertainty. If effective sample size is inadequate, mark BLOCKED rather than lower the gate. Require baseline and candidate to use the same information, risk, liquidity, fees and execution opportunity.

## Capacity and economics

Illustrative EUR500m affected annual balances, converted to USD equivalent for ROI. Limited by replacement-asset depth, settlement access and concentration limits; use <=1% observed daily turnover until calibrated. Capacity and costs are assumptions until measured at executable sizes. Charge bid/ask, impact, funding, financing/borrow where relevant, settlement costs and the stated operating expense. Double spreads/impact and halve assumed capacity in sensitivity analysis.

**Purely illustrative 24-month ROI; assumptions and arithmetic, not empirical evidence.** USD-equivalent affected exposure $500,000,000; annual net benefit scenarios 0/2/4 bps. Value channel: annual net replacement/carry savings in USD-equivalent terms after execution charges. Assume 6 months before benefit starts, 1.5 benefit-years, zero discounting and no terminal value. Two-year all-in engineering/data/review/maintenance cost C=$140,000; this budget is a planning assumption, not a vendor quote. Trading/operating charges are already deducted from scenario benefits; do not deduct them twice.

| Scenario | Annual net benefit before project cost | 24-month benefit B after launch lag | Net ROI (B-C)/C |
|---|---:|---:|---:|
| Downside | $0 | $0 | -100.0% |
| Base | $100,000 | $150,000 | 7.1% |
| Upside | $200,000 | $300,000 | 114.3% |

Break-even annual benefit after launch = $93,333. Full cost is lost if abandoned before benefit; ROI=-100% then. Negative trading/hedge scenarios can be worse than -100%. Utility or avoided-loss scenarios are not guaranteed cash revenue. Budgets and benefits across projects overlap and must not be summed.

## Research value, risk and novelty

**Academic/publication value:** Medium-high: event-time collateral option value, with public framework changes and transparent effective-time tests. **Key risk:** Current eligibility is not historical eligibility; rating changes may be anticipated in prices. Framework eligibility does not establish institution-specific usability, own-use treatment or transfer rights.

**Cumulative novelty check:** Nearest: 2026-11-13/05 eligibility compiler. This consumes structured official changes and chooses when to preposition; it does not translate private agreement prose into constraints. Checked against all 35 archived idea READMEs on main; this is a scoped comparison, not certification of originality in academic literature or inaccessible archives.

## Source ladder and truth state

## 1. Public/free first

- [ECB eligible-assets download and archive](https://www.ecb.europa.eu/mopo/coll/assets/html/list-MID.en.html) — Eligible-asset files and historical snapshots; archive gaps and schema changes disclosed. Historical first-public timestamps still require audit. Retrieval run: 2026-11-17T02:38:22+00:00.
- [ECB eligible-assets user guide](https://www.ecb.europa.eu/mopo/coll/assets/guide/html/index.en.html) — Schema and change codes; does not establish institution-specific eligibility or legal authority. Retrieval run: 2026-11-17T02:38:22+00:00.

## 2. Commercial/licensed

Licensed EUR bond bid/ask and historical rating/terms data; no vendor extracts in the public repository. Rights, fees, coverage, historical availability and redistribution are **BLOCKED** until reviewed; no entitlement is implied.

## 3. Private/permissioned only after public feasibility

Institution-approved eligibility, holdings and transfer permissions; absent. Do not upload these records, extracts, identifiers or research results to this public repository. Public outputs use only permitted aggregate summaries or synthetic fixtures reviewed for disclosure.

## 4. Research background

- [Boyd and Vandenberghe, Convex Optimization](https://web.stanford.edu/~boyd/cvxbook/) — Verified author-hosted textbook. Background for convex relaxations, not evidence of an economic edge or MILP global optimality. Retrieval run: 2026-11-17T02:38:22+00:00.

**Evidence classification:** portal/methodology existence was checked through current public search/retrieval. No data download, license clearance, point-in-time panel, calibrated model, price reaction, realized return or ROI was verified. Public accessibility does not grant blanket redistribution. Links support only the statements attached to them; theoretical papers do not support the new hypothesis.


**Status: DESIGN WRITTEN. Empirical execution, data-rights clearance, package lock, runtime, backtest, shadow trial and production implementation: BLOCKED pending the documented prerequisites. No research model was run.**

## Navigation

[SPEC](SPEC.md) · [PLAN](PLAN.md) · [TASKS](TASKS.md) · [ROADMAP](ROADMAP.md) · [HANDOFF](HANDOFF.md) · [SOURCES](SOURCES.md) · [AGENT](AGENT.md) · [SKILL](SKILL.md) · [PROMPT](PROMPT.md) · [TOOLING](TOOLING.md) · [WORKFLOW](WORKFLOW.md) · [RUNTIME](RUNTIME.md) · [EVALS](EVALS.md)
