# US Bank Deposit Beta and Mark-to-Market Securities Run Risk
**ID:** B17-18 · **Group:** Global/domestic quant research · **Geography:** US regional banks and bank-sector equity/credit · **Priority:** 88/100 · **Status:** not implemented

## Economic decision and hypothesis
Reported uninsured deposits and HTM unrealized losses alone do not measure repricing speed or franchise response.

**Decision:** Assess which banks face funding-cost and securities-loss convexity under uninsured deposit migration.

**H1:** A joint deposit-beta and securities mark-to-market gap predicts earnings/credit deterioration better than uninsured deposit percentage.

## Formulation
```text
NII_i≈Loans_i*r_L - Deposits_i*(r_D0+β_i*Δr) - Wholesale_i*r_W ; StressGap_i=HTMLoss_i+RunOutflow_i*FundingSpread
```
**Variables:** β_i deposit repricing elasticity, HTMLoss published held-to-maturity unrealized loss proxy, RunOutflow scenario.

**Data:** FDIC bank Call Reports, quarterly uninsured deposits, HTM/AFS loss fields, benchmark rates, bank equity CDS

**Clock:** Quarter-end balances become usable only at the first public Call Report publication, not period end.

**Baseline:** Uninsured deposit share plus book capital ratio; **candidate:** Hierarchical deposit beta estimation plus accounting-based duration stress; **advanced:** Agent-based depositor migration with liquidity haircut and contagion sensitivity.

**Evaluation:** Next-quarter NII loss, downside rank precision, capital shortfall, sector-neutral return IC. **Failure:** No incremental forecast versus capital/deposit mix baseline after strict public release lag.

**Capacity:** Large regional bank equity/cash bonds viable; small banks thin, CDS pricing inaccessible and not required for public proxy.

**Illustrative sensitivity:** $155k assumed total 24m development/data/maintenance cost; assumed launch in month 6; assumed annual gross outcome downside/base/upside $0k/$120k/$245k. Resulting 24m net ROI **-100.0% / 16.1% / 137.1% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.

## Documents
[SPEC](./SPEC.md) · [PLAN](./PLAN.md) · [TASKS](./TASKS.md) · [ROADMAP](./ROADMAP.md) · [HANDOFF](./HANDOFF.md) · [SOURCES](./SOURCES.md) · [AGENT](./AGENT.md) · [SKILL](./SKILL.md) · [PROMPT](./PROMPT.md) · [TOOLING](./TOOLING.md) · [WORKFLOW](./WORKFLOW.md) · [RUNTIME](./RUNTIME.md) · [EVALS](./EVALS.md)

**No empirical model execution, licensing approval, dataset download, trading result or implemented AI runtime is claimed.**
