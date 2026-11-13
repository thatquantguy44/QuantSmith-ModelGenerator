# Securities Lending Liquidity Provision Premium
**ID:** QMG-20261112-11 · **Priority:** 87/100 · **Phase:** not started.

## Problem and value
Stable lenders may earn stress-sensitive compensation not captured by unconditional average fees.

**Business decision:** value dependable securities supply during high financing stress. **Hypothesis:** Stress supply resilience predicts financing yield beyond security composition and usage.

## Formulation
```text
R_o,t=α_o+β_o×FinancingStress_t+ε_o,t
```

**Data:** Lender inventory changes, special fees, recalls, utilization, systemic stress factors. **Baseline:** trailing revenue per lendable dollar. **Candidate:** conditional financing factor decomposition. **Advanced:** endogenous supply/fee equilibrium with nonlinear downside beta. **Metrics:** stress carry, stability, adjusted yield and mandate value. **Key risk:** composition and survivorship bias can masquerade as a premium.

**Implementation:** pandas,statsmodels,numpy proposed; difficulty and capacity to be assessed. **Illustrative ROI hypothesis:** 1–3×, not a measured return.

## Research files
[Specification](SPEC.md) · [Plan](PLAN.md) · [Tasks](TASKS.md) · [Roadmap](ROADMAP.md) · [Handoff](HANDOFF.md) · [Sources](SOURCES.md) · [Evaluation](EVALS.md)

## AI and reuse files
[Agent](AGENT.md) · [Skill](SKILL.md) · [Prompt](PROMPT.md) · [Tooling](TOOLING.md) · [Workflow](WORKFLOW.md) · [Runtime](RUNTIME.md)

No model, historical result, source-specific licensing, or claimed publication has been verified.
