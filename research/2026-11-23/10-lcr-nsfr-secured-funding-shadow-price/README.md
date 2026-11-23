# Regulatory LCR/NSFR Shadow Cost of Secured Funding Collateral
**ID:** B17-10 · **Group:** Securities finance · **Geography:** Global banks; US/EU Basel liquidity reporting frameworks · **Priority:** 86/100 · **Status:** not implemented

## Economic decision and hypothesis
A cheap repo can be uneconomic when it reduces HQLA or increases required stable funding disproportionately.

**Decision:** Allocate financing transactions by incremental liquidity-ratio headroom consumption, not only nominal repo spread.

**H1:** Dual-priced LCR/NSFR constraints reorder feasible funding selections and improve all-in liquidity-adjusted economics versus spread ranking.

## Formulation
```text
min_x Σ_i (r_i*x_i + k_i*x_i) subject to HQLA(x)/NetCashOutflows(x)≥LCR_min and ASF(x)/RSF(x)≥NSFR_min, Σ_i x_i≥Need
```
**Variables:** x_i secured funding quantities, k_i legal balance-sheet charge; LCR, ASF, RSF use approved regulatory definitions.

**Data:** Public Basel ratio methodology/aggregate trends, synthetic collateral classes, cashflow ladder and legal-entity matrices

**Clock:** Regulatory rule version, haircut classification and reporting entity apply as of funding decision.

**Baseline:** Rank repo offers by quoted rate subject to gross notional limits; **candidate:** Linear/mixed-integer secured funding allocation with LCR/NSFR dual-price attribution; **advanced:** Scenario-based shadow-price frontier with intraday and quarter-end liquidity risk.

**Evaluation:** All-in liquidity-adjusted cost, marginal dual price, buffer breaches, sensitivity to rule version. **Failure:** No cost difference over conservative liquidity-constrained benchmark or unstable/uninterpretable duals.

**Capacity:** Use only approved internal regulatory measures when available; funding choices constrained by entity/collateral eligibility.

**Illustrative sensitivity:** $180k assumed total 24m development/data/maintenance cost; assumed launch in month 8; assumed annual gross outcome downside/base/upside $0k/$120k/$280k. Resulting 24m net ROI **-100.0% / -11.1% / 107.4% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.

## Documents
[SPEC](./SPEC.md) · [PLAN](./PLAN.md) · [TASKS](./TASKS.md) · [ROADMAP](./ROADMAP.md) · [HANDOFF](./HANDOFF.md) · [SOURCES](./SOURCES.md) · [AGENT](./AGENT.md) · [SKILL](./SKILL.md) · [PROMPT](./PROMPT.md) · [TOOLING](./TOOLING.md) · [WORKFLOW](./WORKFLOW.md) · [RUNTIME](./RUNTIME.md) · [EVALS](./EVALS.md)

**No empirical model execution, licensing approval, dataset download, trading result or implemented AI runtime is claimed.**
