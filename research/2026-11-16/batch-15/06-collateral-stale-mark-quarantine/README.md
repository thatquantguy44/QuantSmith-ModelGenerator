# 06. Collateral Stale-Mark Quarantine and Conservative Valuation

**QMG-20261116-06 · A — Securities finance · Priority 93/100 (editorial judgment)**

**Geography/instruments:** US and euro-area secured financing collateral. **Difficulty:** Medium. **Production feasibility:** High for synthetic data controls; live calibration needs timestamped independent marks. **Effort assumption:** One engineer and a part-time researcher for 6-8 weeks; independent mark rights are a dependency.

## Problem, decision and economic value

A syntactically valid collateral price can be stale or mechanically wrong, overstating secured value and creating false financing capacity. **Decision:** Quarantine a suspect mark or assign a conservative valuation interval, escalating exceptions rather than automatically altering contractual marks. Economic value is measured through the declared target and net cost model, not forecast accuracy alone.

**Hypothesis (untested):** A cross-source temporal-consistency gate reduces unsecured-value underestimation by at least 30% versus last-price carry-forward at an operational false-quarantine rate below 1%.

## Mathematics and decision constraints

```text
V_i^safe=q_i*L_i*(1-h_i); flag_i=1{age_i>a_i or abs(p_i-p_i^ref)>tau_i}; choose thresholds (a,tau) to minimize E[undersecured_loss]+review_cost subject to P(p_i>=L_i|I_t)>=0.99 and false_quarantine<=0.01
```

q quantity; h haircut; L,U independently calibrated price interval; p_ref lag-safe cross-source reference; age time since valid quote; a maximum age; tau asset-specific tolerance, both fitted on training data; I_t available source information. Quarantined marks cannot create funding capacity. This is a conservative monitoring valuation, not an unauthorized contract valuation.

Mathematical conventions: one basis point is 0.0001 of annual rate; dt is the declared year fraction. CVaR_a(L)=min_eta[eta+E[(L-eta)^+]/(1-a)] for loss L and tail level a. Risk/turnover penalties are nonnegative and frozen before holdout; rates, prices, cash and face units must reconcile. All forecasts/expectations are conditional on information available at the decision time. A proposed nonlinear or integer formulation is not asserted convex or globally solved without a solver certificate.

## Data and decision timing

Raw vendor price/event/receive timestamps, currency, clean/dirty convention, coupon accrual, corporate actions, independent quote source and later adjudicated corrections. Public rates and eligible-asset terms support synthetic scenarios, not intraday bond valuation. **Grain:** collateral instrument x mark source x quote/receive event. **Decision clock:** Gate each mark at ingestion before its use in a financing solve; reference marks must be received earlier than the current solve. Labels are adjudications collected later and assigned only to future model training windows.

Every input carries observed_at, published_at, received_at, available_at=max(published_at, received_at), effective_at, source/version/hash and rights_class. Unknown historical release time is not reconstructed from a present-day file timestamp; use the declared conservative lag or exclude the row. In replay, separate an assumed historical ingestion latency from an actually recorded receive time. Outcomes may arrive later but cannot be features.

## Model comparison and evaluation

- **Credible baseline:** Use latest received price within a fixed one-day age limit; otherwise last valid mark with static buffer.
- **Suggested candidate:** Robust cross-source median and asset-specific age/interval rule.
- **Advanced alternative:** State-space price filtering with conformal lower valuation bounds and selective quarantine.
- **Target:** underestimated unsecured exposure and false quarantine burden.
- **Metrics:** value shortfall, interval coverage, false positives, stale detection delay, desk override rate and review hours.
- **Pre-registered stop/go:** GO if underestimation falls >=30%, clean-mark false quarantine <1%, and lower-bound coverage >=99% in stress replay; reject if benefit comes only from excessive haircuts or review burden exceeds 0.5 FTE per 10k instruments.
- **Critical negative test:** Inject a 100x currency/unit error, stale timestamp, ex-coupon drop and two nominally independent marks with identical upstream provenance; detect unit/staleness defects while preserving valid convention changes.

Use chronological development/validation/untouched holdout partitions at the native decision frequency, purging the full target horizon and overlapping event groups. Fit transforms, calibration and policy parameters inside training folds. Cluster uncertainty by the economic event/issuer/season, not by repeated rows; preserve disappeared instruments and failed outcomes. Report all candidate variants and correct selection uncertainty. If effective sample size is inadequate, mark BLOCKED rather than lower the gate. Require baseline and candidate to use the same information, risk, liquidity, fees and execution opportunity.

## Capacity and economics

Illustrative $1bn monitored collateral; benefits are operational hours and conservatively estimated error-loss avoidance, not additive lending alpha. Conservative marks can reduce usable funding capacity. Capacity and costs are assumptions until measured at executable sizes. Charge bid/ask, impact, funding, financing/borrow where relevant, settlement costs and the stated operating expense. Double spreads/impact and halve assumed capacity in sensitivity analysis.

**Purely illustrative 24-month ROI; assumptions and arithmetic, not empirical evidence.** 1,000 annual units x $100/unit x effectiveness 0/0.8/1.6. Value channel: annual hours/errors-equivalent savings: 1,000 hours at $100/hour times scenario effectiveness; loss avoidance excluded. Assume 3 months before benefit starts, 1.75 benefit-years, zero discounting and no terminal value. Two-year all-in engineering/data/review/maintenance cost C=$120,000; this budget is a planning assumption, not a vendor quote. Trading/operating charges are already deducted from scenario benefits; do not deduct them twice.

| Scenario | Annual net benefit before project cost | 24-month benefit B after launch lag | Net ROI (B-C)/C |
|---|---:|---:|---:|
| Downside | $0 | $0 | -100.0% |
| Base | $80,000 | $140,000 | 16.7% |
| Upside | $160,000 | $280,000 | 133.3% |

Break-even annual benefit after launch = $68,571. Full cost is lost if abandoned before benefit; ROI=-100% then. Negative trading/hedge scenarios can be worse than -100%. Utility or avoided-loss scenarios are not guaranteed cash revenue. Budgets and benefits across projects overlap and must not be summed.

## Research value, risk and novelty

**Academic/publication value:** Medium: reproducible error taxonomy and dependence-aware coverage; strongest value may be operational rather than journal novelty. **Key risk:** Independent sources can share the same vendor lineage. Corporate actions and currency factors can look like outliers; later corrections create hindsight labels.

**Cumulative novelty check:** Nearest: 2026-11-13/10 identity reconciliation. Instrument identity is assumed known; this tests price validity and conservative secured value, not cross-system ID matching. Checked against all 35 archived idea READMEs on main; this is a scoped comparison, not certification of originality in academic literature or inaccessible archives.

## Source ladder and truth state

## 1. Public/free first

- [ECB eligible-assets user guide](https://www.ecb.europa.eu/mopo/coll/assets/guide/html/index.en.html) — Schema and change codes; does not establish institution-specific eligibility or legal authority. Retrieval run: 2026-11-17T02:38:22+00:00.
- [Federal Reserve H.15](https://www.federalreserve.gov/releases/h15/) — Published rate series and release schedule; daily observations are not executable intraday bond quotes. Retrieval run: 2026-11-17T02:38:22+00:00.

## 2. Commercial/licensed

Two independently licensed pricing sources with explicit lineage and correction histories. Rights, fees, coverage, historical availability and redistribution are **BLOCKED** until reviewed; no entitlement is implied.

## 3. Private/permissioned only after public feasibility

Authorized collateral marks and independent adjudication records in private infrastructure; absent. Do not upload these records, extracts, identifiers or research results to this public repository. Public outputs use only permitted aggregate summaries or synthetic fixtures reviewed for disclosure.

## 4. Research background

- [Boyd and Vandenberghe, Convex Optimization](https://web.stanford.edu/~boyd/cvxbook/) — Verified author-hosted textbook. Background for convex relaxations, not evidence of an economic edge or MILP global optimality. Retrieval run: 2026-11-17T02:38:22+00:00.

**Evidence classification:** portal/methodology existence was checked through current public search/retrieval. No data download, license clearance, point-in-time panel, calibrated model, price reaction, realized return or ROI was verified. Public accessibility does not grant blanket redistribution. Links support only the statements attached to them; theoretical papers do not support the new hypothesis.


**Status: DESIGN WRITTEN. Empirical execution, data-rights clearance, package lock, runtime, backtest, shadow trial and production implementation: BLOCKED pending the documented prerequisites. No research model was run.**

## Navigation

[SPEC](SPEC.md) · [PLAN](PLAN.md) · [TASKS](TASKS.md) · [ROADMAP](ROADMAP.md) · [HANDOFF](HANDOFF.md) · [SOURCES](SOURCES.md) · [AGENT](AGENT.md) · [SKILL](SKILL.md) · [PROMPT](PROMPT.md) · [TOOLING](TOOLING.md) · [WORKFLOW](WORKFLOW.md) · [RUNTIME](RUNTIME.md) · [EVALS](EVALS.md)
