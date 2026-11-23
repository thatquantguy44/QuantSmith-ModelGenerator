# Securities Loan Retroactive Rate Amendment Revenue Assurance
**ID:** B17-04 · **Group:** Securities finance · **Geography:** Global agent lending / US securities loans · **Priority:** 92/100 · **Status:** not implemented

## Economic decision and hypothesis
Backdated fee changes, rate boundaries and returns can create avoidable invoice differences even without a pricing alpha.

**Decision:** Identify contractually unsupported retroactive fee amendments before invoice posting.

**H1:** Bitemporal contract-and-loan event reconstruction detects more true billing exceptions than end-of-day price reconciliation without increasing false disputes.

## Formulation
```text
Invoice_i=Σ_{d∈loanlife_i} Principal_{i,d} * Fee_{i,d} * DayFraction_d ; Error_i=Invoice_posted_i-Invoice_authorized_i
```
**Variables:** Fee_i,d is effective authorized fee, distinct from late recorded amendment; Principal is open borrow notional.

**Data:** Synthetic loans, amendment lifecycle, dated fee notices, loan terminations, currency and day-count conventions

**Clock:** Invoice run includes only fee amendments authorized and received before invoice cut-off, even if effective date is earlier.

**Baseline:** Latest agreed fee × end-period balance × elapsed days; **candidate:** Bitemporal finite-state rate and loan lifecycle ledger with invariant checks; **advanced:** Probabilistic anomaly prioritization atop an exact contract-aware billing engine.

**Evaluation:** Synthetic exception precision/recall, manual hours, invoice basis-point leakage, false escalation rate. **Failure:** No improvement in high-severity seeded exceptions relative to deterministic ledger, or unauthorized dispute actions.

**Capacity:** Value in avoided losses and less manual rework, not trading alpha; false dispute costs and review minutes cap benefit.

**Illustrative sensitivity:** $105k assumed total 24m development/data/maintenance cost; assumed launch in month 4; assumed annual gross outcome downside/base/upside $0k/$95k/$165k. Resulting 24m net ROI **-100.0% / 50.8% / 161.9% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.

## Documents
[SPEC](./SPEC.md) · [PLAN](./PLAN.md) · [TASKS](./TASKS.md) · [ROADMAP](./ROADMAP.md) · [HANDOFF](./HANDOFF.md) · [SOURCES](./SOURCES.md) · [AGENT](./AGENT.md) · [SKILL](./SKILL.md) · [PROMPT](./PROMPT.md) · [TOOLING](./TOOLING.md) · [WORKFLOW](./WORKFLOW.md) · [RUNTIME](./RUNTIME.md) · [EVALS](./EVALS.md)

**No empirical model execution, licensing approval, dataset download, trading result or implemented AI runtime is claimed.**
