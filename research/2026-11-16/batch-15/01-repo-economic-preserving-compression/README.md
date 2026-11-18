# 01. Repo Compression with Cash-Flow Preservation

**QMG-20261116-01 · A — Securities finance · Priority 94/100 (editorial judgment)**

**Geography/instruments:** US Treasury repo; one legal netting set at a time. **Difficulty:** High. **Production feasibility:** Synthetic solver prototype feasible; live adoption blocked by consent and legal eligibility. **Effort assumption:** Two researchers/engineers for 10-14 weeks; legal review is a separate dependency.

## Problem, decision and economic value

Offsetting repo tickets can consume settlement messages and gross operational capacity even when net cash and security obligations are small. **Decision:** Select existing tickets to tear up or resize without changing each participant's dated cash and CUSIP obligations. Economic value is measured through the declared target and net cost model, not forecast accuracy alone.

**Hypothesis (untested):** An economics-preserving compression reduces eligible gross ticket notional by at least 15% and operational cost by at least 10% versus bilateral pair cancellation, with no additional settlement or market risk.

## Mathematics and decision constraints

```text
min_(x,z) sum_e a_e*x_e + k_e*z_e; A*x=A*q, D*x=D*q, 0<=x_e<=q_e, x_e<=M_e*z_e, z_e in {0,1}, x_e=lot_e*m_e, m_e integer
```

e indexes consenting tickets within the same legally approved set; q and x are original and retained face amounts; A maps tickets to dated participant/CUSIP flows; D maps them to dated cash flows including accrued repo interest; a is gross-capacity cost per face dollar; k is per-ticket cost; z marks retained tickets; M=q; lot is the permitted denomination.

Mathematical conventions: one basis point is 0.0001 of annual rate; dt is the declared year fraction. CVaR_a(L)=min_eta[eta+E[(L-eta)^+]/(1-a)] for loss L and tail level a. Risk/turnover penalties are nonnegative and frozen before holdout; rates, prices, cash and face units must reconcile. All forecasts/expectations are conditional on information available at the decision time. A proposed nonlinear or integer formulation is not asserted convex or globally solved without a solver certificate.

## Data and decision timing

Ticket ID, legal-set ID, participant pseudonym, CUSIP, start/end timestamps, cash principal, accrued interest, rate convention, face amount, consent flag and minimum lot. Public rules plus synthetic networks first; public aggregates cannot reconstruct a private trade graph. **Grain:** repo ticket and dated cash/security obligation. **Decision clock:** Freeze the ledger at 14:00 America/New_York; use only confirmed records ingested by 13:55 and decisions before the relevant service cutoff. Cash-flow amendments received later enter the next solve.

Every input carries observed_at, published_at, received_at, available_at=max(published_at, received_at), effective_at, source/version/hash and rights_class. Unknown historical release time is not reconstructed from a present-day file timestamp; use the declared conservative lag or exclude the row. In replay, separate an assumed historical ingestion latency from an actually recorded receive time. Outcomes may arrive later but cannot be features.

## Model comparison and evaluation

- **Credible baseline:** Cancel exact opposite tickets bilaterally within a legal set; otherwise hold the original book.
- **Suggested candidate:** Mixed-integer minimum-cost circulation with exact cash-flow conservation.
- **Advanced alternative:** Robust multi-period compression with consent uncertainty and settlement-feasibility cuts.
- **Target:** retained gross notional and verified per-date cash/security conservation.
- **Metrics:** gross reduction, message reduction, all-in cost, maximum flow residual, consent acceptance and solve time.
- **Pre-registered stop/go:** GO only with >=15% gross reduction and >=10% realized operational cost reduction on held-out eligible sets; every cash/security residual <=$0.01 cash or zero security units; zero consent violations. STOP on any economic transfer or if gains vanish after legal filtering.
- **Critical negative test:** Construct a three-node cycle with mismatched maturity dates: it must remain uncompressed; changing one consent flag must remove every affected action.

Use chronological development/validation/untouched holdout partitions at the native decision frequency, purging the full target horizon and overlapping event groups. Fit transforms, calibration and policy parameters inside training folds. Cluster uncertainty by the economic event/issuer/season, not by repeated rows; preserve disappeared instruments and failed outcomes. Report all candidate variants and correct selection uncertainty. If effective sample size is inadequate, mark BLOCKED rather than lower the gate. Require baseline and candidate to use the same information, risk, liquidity, fees and execution opportunity.

## Capacity and economics

Illustrative $1bn eligible matched book; no directional risk capital assumed. Economics come from fewer messages and approved gross-capacity charges, not treating all removed notional as regulatory capital relief. Capacity and costs are assumptions until measured at executable sizes. Charge bid/ask, impact, funding, financing/borrow where relevant, settlement costs and the stated operating expense. Double spreads/impact and halve assumed capacity in sensitivity analysis.

**Purely illustrative 24-month ROI; assumptions and arithmetic, not empirical evidence.** USD-equivalent affected exposure $1,000,000,000; annual net benefit scenarios 0/0.75/1.5 bps. Value channel: annual operational/gross-capacity cost saved on eligible matched notional; no automatic regulatory capital benefit. Assume 6 months before benefit starts, 1.5 benefit-years, zero discounting and no terminal value. Two-year all-in engineering/data/review/maintenance cost C=$180,000; this budget is a planning assumption, not a vendor quote. Trading/operating charges are already deducted from scenario benefits; do not deduct them twice.

| Scenario | Annual net benefit before project cost | 24-month benefit B after launch lag | Net ROI (B-C)/C |
|---|---:|---:|---:|
| Downside | $0 | $0 | -100.0% |
| Base | $75,000 | $112,500 | -37.5% |
| Upside | $150,000 | $225,000 | 25.0% |

Break-even annual benefit after launch = $120,000. Full cost is lost if abandoned before benefit; ROI=-100% then. Negative trading/hedge scenarios can be worse than -100%. Utility or avoided-loss scenarios are not guaranteed cash revenue. Budgets and benefits across projects overlap and must not be summed.

## Research value, risk and novelty

**Academic/publication value:** Medium: constrained compression with dated multi-asset conservation; novelty relative to existing compression literature needs a dedicated review. **Key risk:** Legal netting is not created by algebra; different dates, rates and counterparties must not be silently offset. Synthetic network density can overstate capacity.

**Cumulative novelty check:** Nearest: 2026-11-13/01 clearing access. That project chooses a clearing route; this preserves a fixed book's economics while removing tickets, with clearing access held fixed. Checked against all 35 archived idea READMEs on main; this is a scoped comparison, not certification of originality in academic literature or inaccessible archives.

## Source ladder and truth state

## 1. Public/free first

- [DTCC repo service description](https://www.dtcc.com/clearing-and-settlement-services/ficc-gov/repo) — Service context only; no claim that proposed compression is a supported product or legally permissible for every trade. Retrieval run: 2026-11-17T02:38:22+00:00.
- [OFR repo data release](https://www.financialresearch.gov/short-term-funding-monitor/datasets/repo/) — Aggregate rates and volumes; preliminary and final series have different release timing. Not executable quotes or a contractual fallback rate. Retrieval run: 2026-11-17T02:38:22+00:00.

## 2. Commercial/licensed

Licensed trade-processing/reference-data tools only if public rules and synthetic fixtures are insufficient; legal and consent records remain permissioned. Rights, fees, coverage, historical availability and redistribution are **BLOCKED** until reviewed; no entitlement is implied.

## 3. Private/permissioned only after public feasibility

Authorized repo ledger and legal-set approvals in a private deployment; none obtained or committed. Do not upload these records, extracts, identifiers or research results to this public repository. Public outputs use only permitted aggregate summaries or synthetic fixtures reviewed for disclosure.

## 4. Research background

- [Boyd and Vandenberghe, Convex Optimization](https://web.stanford.edu/~boyd/cvxbook/) — Verified author-hosted textbook. Background for convex relaxations, not evidence of an economic edge or MILP global optimality. Retrieval run: 2026-11-17T02:38:22+00:00.

**Evidence classification:** portal/methodology existence was checked through current public search/retrieval. No data download, license clearance, point-in-time panel, calibrated model, price reaction, realized return or ROI was verified. Public accessibility does not grant blanket redistribution. Links support only the statements attached to them; theoretical papers do not support the new hypothesis.


**Status: DESIGN WRITTEN. Empirical execution, data-rights clearance, package lock, runtime, backtest, shadow trial and production implementation: BLOCKED pending the documented prerequisites. No research model was run.**

## Navigation

[SPEC](SPEC.md) · [PLAN](PLAN.md) · [TASKS](TASKS.md) · [ROADMAP](ROADMAP.md) · [HANDOFF](HANDOFF.md) · [SOURCES](SOURCES.md) · [AGENT](AGENT.md) · [SKILL](SKILL.md) · [PROMPT](PROMPT.md) · [TOOLING](TOOLING.md) · [WORKFLOW](WORKFLOW.md) · [RUNTIME](RUNTIME.md) · [EVALS](EVALS.md)
