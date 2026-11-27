# Biotech FDA Catalyst Probability versus Options Event Premium
**ID:** B17-16 · **Group:** Global/domestic quant research · **Geography:** US small/mid-cap biotech equity and listed options · **Priority:** 90/100 · **Status:** not implemented

## Economic decision and hypothesis
Catalyst calendars are susceptible to hindsight because FDA decision timing, clinical surprises and halted quotes interact.

**Decision:** Test whether equity option implied event moves overstate conditional post-decision realized jumps at fixed risk limits.

**H1:** Official pre-event regulatory state improves risk-adjusted event-volatility pricing relative to a generic historical event move.

## Formulation
```text
ExpectedJumpVar_i=Σ_s p_{i,s}*(log(P_{after,s}/P_before))^2; VRP_i=ImpliedEventVar_i-ExpectedJumpVar_i-Cost_i
```
**Variables:** s approval/rejection/delay states, p_s probabilities estimated strictly pre-decision; VRP is variance risk premium.

**Data:** FDA event dates, approval histories, pre-event public filings, full options surfaces, equity halt and event-time trades

**Clock:** No use of FDA outcome until public approval announcement; option quotes at last feasible pre-event time.

**Baseline:** Historical absolute event returns grouped by market cap and indication; **candidate:** Regulatory-document event taxonomy + shrinkage conditional jump model; **advanced:** Hierarchical Bayesian decision-state model and option-neutral density decomposition.

**Evaluation:** Jump variance calibration, option VRP after costs, event coverage, tail hedge error. **Failure:** Conditional probability model fails event-matched calibration or net executable option premium.

**Capacity:** Biotech option spreads and gap risk severe; define small budget and loss limit before evaluating.

**Illustrative sensitivity:** $195k assumed total 24m development/data/maintenance cost; assumed launch in month 9; assumed annual gross outcome downside/base/upside $0k/$110k/$295k. Resulting 24m net ROI **-100.0% / -29.5% / 89.1% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.

## Documents
[SPEC](./SPEC.md) · [PLAN](./PLAN.md) · [TASKS](./TASKS.md) · [ROADMAP](./ROADMAP.md) · [HANDOFF](./HANDOFF.md) · [SOURCES](./SOURCES.md) · [AGENT](./AGENT.md) · [SKILL](./SKILL.md) · [PROMPT](./PROMPT.md) · [TOOLING](./TOOLING.md) · [WORKFLOW](./WORKFLOW.md) · [RUNTIME](./RUNTIME.md) · [EVALS](./EVALS.md)

**No empirical model execution, licensing approval, dataset download, trading result or implemented AI runtime is claimed.**
