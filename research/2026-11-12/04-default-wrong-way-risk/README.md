# Borrower Default Wrong-Way Risk Optimization
**ID:** QMG-20261112-04 · **Priority:** 94/100 · **Phase:** not started.

## Problem and value
Borrower default can coincide with loaned-security appreciation and collateral liquidation stress.

**Business decision:** price borrower limits, haircut and contingent indemnification. **Hypothesis:** Joint default-exposure modeling finds stressed loss missed by independent PD/haircut rules.

## Formulation
```text
Loss=1{default≤T}×max(ReplacementValue-CollateralProceeds,0)
```

**Data:** Counterparty credit, collateral, contract closeout provisions, stress price and liquidity history. **Baseline:** independent PD times static haircut. **Candidate:** correlated default/exposure Monte Carlo. **Advanced:** stochastic-intensity wrong-way closeout with price impact. **Metrics:** stress ES, loss calibration, limits used and risk-adjusted P&L. **Key risk:** sparse default observations and unidentifiable tail parameters.

**Implementation:** numpy,scipy,statsmodels proposed; difficulty and capacity to be assessed. **Illustrative ROI hypothesis:** 2–4×, not a measured return.

## Research files
[Specification](SPEC.md) · [Plan](PLAN.md) · [Tasks](TASKS.md) · [Roadmap](ROADMAP.md) · [Handoff](HANDOFF.md) · [Sources](SOURCES.md) · [Evaluation](EVALS.md)

## AI and reuse files
[Agent](AGENT.md) · [Skill](SKILL.md) · [Prompt](PROMPT.md) · [Tooling](TOOLING.md) · [Workflow](WORKFLOW.md) · [Runtime](RUNTIME.md)

No model, historical result, source-specific licensing, or claimed publication has been verified.
