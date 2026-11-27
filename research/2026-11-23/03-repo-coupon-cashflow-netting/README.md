# Repo Coupon and Principal Event Cash-Flow Netting Scheduler
**ID:** B17-03 · **Group:** Securities finance · **Geography:** US Treasuries, agencies and multi-currency repo · **Priority:** 93/100 · **Status:** not implemented

## Economic decision and hypothesis
Security cash-flow dates and bilateral payment terms can create avoidable gross cash movements even when net exposure is small.

**Decision:** Minimize same-day cash deficits caused by collateral coupon/principal flows and contractual manufactured payments.

**H1:** Event-aware legally permissible netting reduces liquidity buffer and operational exceptions versus cash-flow-independent settlement.

## Formulation
```text
min_{f_{ij,t},B_t} Σ_t (c_B*B_t+c_F*|f_t|) s.t. Cash_t + B_t + inflow_t - outflow_t ≥0; NettingSet_{ij}=1
```
**Variables:** f_ij,t are settlement payment flows; B_t is funding buffer; NettingSet is legal contractual binary.

**Data:** Public bond schedules, ex-coupon dates, settlement calendars, synthetic counterparties and netting agreements

**Clock:** Coupon schedule published at issuance; adjustments and confirmed obligations only after contract notice timestamp.

**Baseline:** Gross independent payment processing with static buffer; **candidate:** Mixed-integer liquidity scheduling with eligibility/netting-set constraints; **advanced:** Stochastic event-flow MPC with missed payment penalties and legal-entity netting restrictions.

**Evaluation:** Peak cash buffer, gross payment count, exception cost, settlement timeliness. **Failure:** No capacity-adjusted cost reduction versus pre-netted conventional operations or violations of payment rights.

**Capacity:** Savings limited to payments legally eligible for netting; reconciliation costs, daylight overdraft fees and solver latency included.

**Illustrative sensitivity:** $120k assumed total 24m development/data/maintenance cost; assumed launch in month 5; assumed annual gross outcome downside/base/upside $0k/$95k/$190k. Resulting 24m net ROI **-100.0% / 25.3% / 150.7% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.

## Documents
[SPEC](./SPEC.md) · [PLAN](./PLAN.md) · [TASKS](./TASKS.md) · [ROADMAP](./ROADMAP.md) · [HANDOFF](./HANDOFF.md) · [SOURCES](./SOURCES.md) · [AGENT](./AGENT.md) · [SKILL](./SKILL.md) · [PROMPT](./PROMPT.md) · [TOOLING](./TOOLING.md) · [WORKFLOW](./WORKFLOW.md) · [RUNTIME](./RUNTIME.md) · [EVALS](./EVALS.md)

**No empirical model execution, licensing approval, dataset download, trading result or implemented AI runtime is claimed.**
