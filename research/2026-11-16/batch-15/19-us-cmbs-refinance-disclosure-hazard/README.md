# 19. US CMBS Refinance Hazard from Public Disclosures

**QMG-20261116-19 · B — Domestic/global quant markets · Priority 86/100 (editorial judgment)**

**Geography/instruments:** United States commercial property and securitized credit. **Difficulty:** High. **Production feasibility:** Public ABS-EE parser prototype feasible; price/backtest panel and representative history require further rights checks. **Effort assumption:** One credit researcher and one structured-document engineer for 12-16 weeks.

## Problem, decision and economic value

A commercial mortgage approaching maturity can be extended, refinanced, modified or defaulted; a single debt-service ratio misses competing outcomes and refinancing-rate reset. **Decision:** Limit public CMBS/REIT credit exposure according to released refinance cash-flow gaps and competing maturity outcomes. Economic value is measured through the declared target and net cost model, not forecast accuracy alone.

**Hypothesis (untested):** A vintage-safe competing-risk model improves 12-month refinancing-distress Brier score by at least 10% versus maturity wall plus current DSCR and lowers stress portfolio loss by 5% at equal spread carry.

## Mathematics and decision constraints

```text
h_k(t|X)=P(event_k at t|survival_t,X_available); gap=max(balance-LTV_max*NOI/cap_rate,0); min_w CVaR_95(loss(w,h))+lambda*turnover, spread_carry>=C, issuer_weight<=0.05
```

k is refinance, extension, modification or distress; NOI net operating income as publicly reported; cap_rate scenario valuation yield; LTV_max declared refinance limit; w bond/issuer exposures; C baseline spread-carry floor. Scenario cap rates are assumptions, not current appraisals.

Mathematical conventions: one basis point is 0.0001 of annual rate; dt is the declared year fraction. CVaR_a(L)=min_eta[eta+E[(L-eta)^+]/(1-a)] for loss L and tail level a. Risk/turnover penalties are nonnegative and frozen before holdout; rates, prices, cash and face units must reconcile. All forecasts/expectations are conditional on information available at the decision time. A proposed nonlinear or integer formulation is not asserted convex or globally solved without a solver certificate.

## Data and decision timing

Public ABS-EE/10-D/10-K filings, accepted timestamps, loan maturity/amendment histories, NOI/DSCR field definitions, property type, rate terms and outcome reports; licensed bond/REIT pricing and servicing histories as needed. An example filing does not establish complete coverage. **Grain:** loan x public reporting vintage x maturity/outcome event. **Decision clock:** Update risk after SEC acceptance plus one business day parsing/review; a prior reporting month's NOI remains unavailable until filing. Amendments are appended and never rewrite earlier risk snapshots.

Every input carries observed_at, published_at, received_at, available_at=max(published_at, received_at), effective_at, source/version/hash and rights_class. Unknown historical release time is not reconstructed from a present-day file timestamp; use the declared conservative lag or exclude the row. In replay, separate an assumed historical ingestion latency from an actually recorded receive time. Outcomes may arrive later but cannot be features.

## Model comparison and evaluation

- **Credible baseline:** Logistic distress model using months-to-maturity and last publicly available DSCR with fixed rate-shock scenarios.
- **Suggested candidate:** Competing-risk survival model with refinance cash-gap covariates.
- **Advanced alternative:** Hierarchical property-cycle hazard and cash-flow waterfall scenario optimization.
- **Target:** 12-month competing refinance outcomes and portfolio loss at fixed spread carry.
- **Metrics:** Brier/calibration, distress precision-recall, vintage drift, stress loss, carry retained and concentration.
- **Pre-registered stop/go:** GO if Brier improves >=10% and stress loss falls >=5% at same carry over a held-out issuance vintage; STOP if modification histories, exited loans or outcome timing are missing for >10% of sample.
- **Critical negative test:** Replace an original loan maturity with a later extension and verify earlier features remain unchanged; include liquidated loans and enforce waterfall conservation under default scenarios.

Use chronological development/validation/untouched holdout partitions at the native decision frequency, purging the full target horizon and overlapping event groups. Fit transforms, calibration and policy parameters inside training folds. Cluster uncertainty by the economic event/issuer/season, not by repeated rows; preserve disappeared instruments and failed outcomes. Report all candidate variants and correct selection uncertainty. If effective sample size is inadequate, mark BLOCKED rather than lower the gate. Require baseline and candidate to use the same information, risk, liquidity, fees and execution opportunity.

## Capacity and economics

Illustrative $50m credit exposure; position limits depend on tranche liquidity and loss subordination. No assumption that a loan risk score is directly tradable or every CMBS has a liquid hedge. Capacity and costs are assumptions until measured at executable sizes. Charge bid/ask, impact, funding, financing/borrow where relevant, settlement costs and the stated operating expense. Double spreads/impact and halve assumed capacity in sensitivity analysis.

**Purely illustrative 24-month ROI; assumptions and arithmetic, not empirical evidence.** USD-equivalent affected exposure $50,000,000; annual net benefit scenarios -10/20/60 bps. Value channel: annual incremental credit-loss/risk-control value net of hedge and liquidity cost; cash-equivalent planning sensitivity, not observed spread alpha. Assume 9 months before benefit starts, 1.25 benefit-years, zero discounting and no terminal value. Two-year all-in engineering/data/review/maintenance cost C=$180,000; this budget is a planning assumption, not a vendor quote. Trading/operating charges are already deducted from scenario benefits; do not deduct them twice.

| Scenario | Annual net benefit before project cost | 24-month benefit B after launch lag | Net ROI (B-C)/C |
|---|---:|---:|---:|
| Downside | $-50,000 | $-62,500 | -134.7% |
| Base | $100,000 | $125,000 | -30.6% |
| Upside | $300,000 | $375,000 | 108.3% |

Break-even annual benefit after launch = $144,000. Full cost is lost if abandoned before benefit; ROI=-100% then. Negative trading/hedge scenarios can be worse than -100%. Utility or avoided-loss scenarios are not guaranteed cash revenue. Budgets and benefits across projects overlap and must not be summed.

## Research value, risk and novelty

**Academic/publication value:** High: public disclosure vintages and competing refinancing paths; publication depends on reliable field extraction and sample representativeness. **Key risk:** Surviving securitizations and amended files omit failed/removed loans; appraisals lag. Tranche waterfalls and selection into public deals prevent loan-level risk from mapping directly to bond P&L.

**Cumulative novelty check:** Nearest: 2026-11-13/16 corporate bond/ETF liquidity. This predicts commercial-mortgage maturity outcomes and credit cash flows, independent of ETF NAV and corporate-bond transaction liquidity. Checked against all 35 archived idea READMEs on main; this is a scoped comparison, not certification of originality in academic literature or inaccessible archives.

## Source ladder and truth state

## 1. Public/free first

- [SEC EDGAR APIs](https://www.sec.gov/search-filings/edgar-application-programming-interfaces) — Submissions and XBRL API documentation; document-specific parsing and acceptance times still required. Retrieval run: 2026-11-17T02:38:22+00:00.
- [SEC CMBS ABS-EE filing index example](https://www.sec.gov/Archives/edgar/data/1258361/000153949726002880/0001539497-26-002880-index.htm) — Existence of public ABS-EE filings; no assertion that this single filing contains every field or a representative loan panel. Retrieval run: 2026-11-17T02:38:22+00:00.

## 2. Commercial/licensed

Licensed servicing, CMBS waterfall and executable bond-price history; public filings may not cover all required terms. Rights, fees, coverage, historical availability and redistribution are **BLOCKED** until reviewed; no entitlement is implied.

## 3. Private/permissioned only after public feasibility

Optional authorized portfolio constraints; no borrower documents or nonpublic property records obtained. Do not upload these records, extracts, identifiers or research results to this public repository. Public outputs use only permitted aggregate summaries or synthetic fixtures reviewed for disclosure.

## 4. Research background

- [Boyd and Vandenberghe, Convex Optimization](https://web.stanford.edu/~boyd/cvxbook/) — Verified author-hosted textbook. Background for convex relaxations, not evidence of an economic edge or MILP global optimality. Retrieval run: 2026-11-17T02:38:22+00:00.

**Evidence classification:** portal/methodology existence was checked through current public search/retrieval. No data download, license clearance, point-in-time panel, calibrated model, price reaction, realized return or ROI was verified. Public accessibility does not grant blanket redistribution. Links support only the statements attached to them; theoretical papers do not support the new hypothesis.


**Status: DESIGN WRITTEN. Empirical execution, data-rights clearance, package lock, runtime, backtest, shadow trial and production implementation: BLOCKED pending the documented prerequisites. No research model was run.**

## Navigation

[SPEC](SPEC.md) · [PLAN](PLAN.md) · [TASKS](TASKS.md) · [ROADMAP](ROADMAP.md) · [HANDOFF](HANDOFF.md) · [SOURCES](SOURCES.md) · [AGENT](AGENT.md) · [SKILL](SKILL.md) · [PROMPT](PROMPT.md) · [TOOLING](TOOLING.md) · [WORKFLOW](WORKFLOW.md) · [RUNTIME](RUNTIME.md) · [EVALS](EVALS.md)
