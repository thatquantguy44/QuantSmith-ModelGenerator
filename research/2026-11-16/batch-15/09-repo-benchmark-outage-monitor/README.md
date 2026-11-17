# 09. Repo Benchmark Outage and Revision Risk Monitor

**QMG-20261116-09 · A — Securities finance · Priority 89/100 (editorial judgment)**

**Geography/instruments:** United States overnight secured funding. **Difficulty:** Medium. **Production feasibility:** High for public publication/revision monitoring; contractual rate use expressly excluded. **Effort assumption:** One data engineer and part-time researcher for 4-6 weeks.

## Problem, decision and economic value

A published reference rate can be delayed, revised or computed under a disclosed contingency; downstream analytics can treat unlike publication states as equivalent. **Decision:** Choose whether a funding-risk report may use a published rate, show an uncertainty interval, or require manual review; never replace a contractual fallback. Economic value is measured through the declared target and net cost model, not forecast accuracy alone.

**Hypothesis (untested):** A publication-state monitor lowers material funding-risk reporting errors by at least 50% versus blindly carrying the last rate, with false escalation on fewer than 2% of ordinary releases.

## Mathematics and decision constraints

```text
action_t=argmin_(a in {accept,interval,review}) E[L(a,r_true)|I_t] + review_cost(a); interval=[r_hat-z*sigma,r_hat+z*sigma], coverage>=0.99; contractual_rate=official_contract_rule
```

r_true is final same-day reference rate used solely as later evaluation label; I_t contains previously published rates, release state and notes; r_hat monitoring estimate; sigma forecast uncertainty; z calibrated using training-only residuals. L dollar reporting loss uses fixed rate-sensitive exposure and time fraction.

Mathematical conventions: one basis point is 0.0001 of annual rate; dt is the declared year fraction. CVaR_a(L)=min_eta[eta+E[(L-eta)^+]/(1-a)] for loss L and tail level a. Risk/turnover penalties are nonnegative and frozen before holdout; rates, prices, cash and face units must reconcile. All forecasts/expectations are conditional on information available at the decision time. A proposed nonlinear or integer formulation is not asserted convex or globally solved without a solver certificate.

## Data and decision timing

Official rate releases, first-observed timestamps, revision footnotes, contingency notices, rates and ranges; OFR lagged aggregates may inform monitoring but are not contract benchmark substitutes. **Grain:** reference rate x publication event x revision version. **Decision clock:** Snapshot at 08:15 America/New_York and again after verified revisions; only information received by each timestamp is usable. A 14:30 revision must not overwrite the morning feature snapshot.

Every input carries observed_at, published_at, received_at, available_at=max(published_at, received_at), effective_at, source/version/hash and rights_class. Unknown historical release time is not reconstructed from a present-day file timestamp; use the declared conservative lag or exclude the row. In replay, separate an assumed historical ingestion latency from an actually recorded receive time. Outcomes may arrive later but cannot be features.

## Model comparison and evaluation

- **Credible baseline:** Carry the most recent official rate and mark missing releases only after end of day.
- **Suggested candidate:** Versioned publication-state rules plus robust short-horizon rate interval.
- **Advanced alternative:** Regime-switching Bayesian filtering with missing-source stress and calibrated selective reporting.
- **Target:** reporting error and escalation burden under delayed/corrected publication.
- **Metrics:** basis-point error, dollar sensitivity error, interval coverage, false escalations, detection latency and audit completeness.
- **Pre-registered stop/go:** GO if >=50% reduction in material (>2 bp monitoring error) incidents and <2% false escalation over >=250 releases plus synthetic outages; interval coverage >=99%. STOP if rare-event evidence cannot separate improvement from excessive review.
- **Critical negative test:** Hide a morning release and reveal a later correction: morning output must stay immutable and explicitly uncertain; no synthetic estimate may populate a contractual-rate field.

Use chronological development/validation/untouched holdout partitions at the native decision frequency, purging the full target horizon and overlapping event groups. Fit transforms, calibration and policy parameters inside training folds. Cluster uncertainty by the economic event/issuer/season, not by repeated rows; preserve disappeared instruments and failed outcomes. Report all candidate variants and correct selection uncertainty. If effective sample size is inadequate, mark BLOCKED rather than lower the gate. Require baseline and candidate to use the same information, risk, liquidity, fees and execution opportunity.

## Capacity and economics

Illustrative $1bn rate-sensitive monitored exposure; no trading position. Economic value is analyst time and correction effort; excluded speculative avoided trading losses. Capacity and costs are assumptions until measured at executable sizes. Charge bid/ask, impact, funding, financing/borrow where relevant, settlement costs and the stated operating expense. Double spreads/impact and halve assumed capacity in sensitivity analysis.

**Purely illustrative 24-month ROI; assumptions and arithmetic, not empirical evidence.** 700 annual units x $100/unit x effectiveness 0/1/1.8. Value channel: annual analyst/reconciliation hours saved at $100/hour; no assumed alpha or contractual settlement savings. Assume 3 months before benefit starts, 1.75 benefit-years, zero discounting and no terminal value. Two-year all-in engineering/data/review/maintenance cost C=$90,000; this budget is a planning assumption, not a vendor quote. Trading/operating charges are already deducted from scenario benefits; do not deduct them twice.

| Scenario | Annual net benefit before project cost | 24-month benefit B after launch lag | Net ROI (B-C)/C |
|---|---:|---:|---:|
| Downside | $0 | $0 | -100.0% |
| Base | $70,000 | $122,500 | 36.1% |
| Upside | $126,000 | $220,500 | 145.0% |

Break-even annual benefit after launch = $51,429. Full cost is lost if abandoned before benefit; ROI=-100% then. Negative trading/hedge scenarios can be worse than -100%. Utility or avoided-loss scenarios are not guaranteed cash revenue. Budgets and benefits across projects overlap and must not be summed.

## Research value, risk and novelty

**Academic/publication value:** Medium: benchmark-data resilience and reproducible counterfactual outages; rare events limit generalization. **Key risk:** Contingency/revision events are rare; injected outages are software stress tests, not evidence of historical economic benefit. OFR mean rates and official medians differ in coverage.

**Cumulative novelty check:** Nearest: 2026-11-13/04 venue fragmentation. This validates publication state and revisions for operational reporting; it does not infer funding-venue stress or build a tradable nowcast. Checked against all 35 archived idea READMEs on main; this is a scoped comparison, not certification of originality in academic literature or inaccessible archives.

## Source ladder and truth state

## 1. Public/free first

- [New York Fed reference-rate methodology](https://www.newyorkfed.org/markets/reference-rates/additional-information-about-reference-rates) — Official methodology, revision and contingency rules; portal checked, underlying transaction records are not public here. Retrieval run: 2026-11-17T02:38:22+00:00.
- [OFR repo data release](https://www.financialresearch.gov/short-term-funding-monitor/datasets/repo/) — Aggregate rates and volumes; preliminary and final series have different release timing. Not executable quotes or a contractual fallback rate. Retrieval run: 2026-11-17T02:38:22+00:00.

## 2. Commercial/licensed

Optional licensed real-time reference-rate dissemination feed; source-level availability metadata required. Rights, fees, coverage, historical availability and redistribution are **BLOCKED** until reviewed; no entitlement is implied.

## 3. Private/permissioned only after public feasibility

Report sensitivities and incident adjudication logs for private testing; absent. Do not upload these records, extracts, identifiers or research results to this public repository. Public outputs use only permitted aggregate summaries or synthetic fixtures reviewed for disclosure.

## 4. Research background

No idea-specific empirical paper was verified in this run. Do not invent one. A focused literature review is BLOCKED pending implementation; the proposal is not a literature novelty claim.

**Evidence classification:** portal/methodology existence was checked through current public search/retrieval. No data download, license clearance, point-in-time panel, calibrated model, price reaction, realized return or ROI was verified. Public accessibility does not grant blanket redistribution. Links support only the statements attached to them; theoretical papers do not support the new hypothesis.


**Status: DESIGN WRITTEN. Empirical execution, data-rights clearance, package lock, runtime, backtest, shadow trial and production implementation: BLOCKED pending the documented prerequisites. No research model was run.**

## Navigation

[SPEC](SPEC.md) · [PLAN](PLAN.md) · [TASKS](TASKS.md) · [ROADMAP](ROADMAP.md) · [HANDOFF](HANDOFF.md) · [SOURCES](SOURCES.md) · [AGENT](AGENT.md) · [SKILL](SKILL.md) · [PROMPT](PROMPT.md) · [TOOLING](TOOLING.md) · [WORKFLOW](WORKFLOW.md) · [RUNTIME](RUNTIME.md) · [EVALS](EVALS.md)
