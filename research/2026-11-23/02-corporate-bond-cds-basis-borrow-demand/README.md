# Corporate Bond Securities Lending from CDS Basis Hedge Demand
**ID:** B17-02 · **Group:** Securities finance · **Geography:** US and European investment-grade / high-yield credit · **Priority:** 94/100 · **Status:** not implemented

## Economic decision and hypothesis
Bond loan fee and borrow utilization can rise when short-bond/long-CDS trades require physical inventory, but cash-bond liquidity masks causality.

**Decision:** Allocate bond lending supply to CDS-bond basis hedging demand with counterparty and liquidity limits.

**H1:** CDS-bond basis dislocations predict incremental observable bond borrowing demand after conditioning on issue float, liquidity and credit stress.

## Formulation
```text
E[BorrowDemand_{i,t+1}|F_t]=f(Basis_{i,t},Float_i,Liquidity_{i,t}); max_q Σ_i q_i*(fee_i - failCost_i) with q_i≤available_i
```
**Variables:** Basis=CDS spread minus matched cash-bond spread; q_i is feasible bond loan notional; borrower behavior must be estimated.

**Data:** CUSIP-level corporate bond lending fees/locates, CDS curves, TRACE trade activity, issue amount, corporate actions

**Clock:** CDS and cash-bond spreads only after published executable quote times; lending fills observed subsequently.

**Baseline:** Trailing borrower request count and issue-size utilization; **candidate:** Matched event study plus borrow-arrival hazard conditional on CDS-bond basis; **advanced:** Structural joint CDS/bond market-maker inventory model with selection-corrected demand.

**Evaluation:** Borrow-arrival log score, realized net fee improvement, stale quote rate and borrow supply capacity. **Failure:** Estimated basis effects fail paired holdouts or increase rejected locates after slippage and liquidity controls.

**Capacity:** Bond borrow capacity and transaction costs can overwhelm narrow basis; never equate public volume with tradable borrow.

**Illustrative sensitivity:** $150k assumed total 24m development/data/maintenance cost; assumed launch in month 7; assumed annual gross outcome downside/base/upside $0k/$110k/$230k. Resulting 24m net ROI **-100.0% / 3.9% / 117.2% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.

## Documents
[SPEC](./SPEC.md) · [PLAN](./PLAN.md) · [TASKS](./TASKS.md) · [ROADMAP](./ROADMAP.md) · [HANDOFF](./HANDOFF.md) · [SOURCES](./SOURCES.md) · [AGENT](./AGENT.md) · [SKILL](./SKILL.md) · [PROMPT](./PROMPT.md) · [TOOLING](./TOOLING.md) · [WORKFLOW](./WORKFLOW.md) · [RUNTIME](./RUNTIME.md) · [EVALS](./EVALS.md)

**No empirical model execution, licensing approval, dataset download, trading result or implemented AI runtime is claimed.**
