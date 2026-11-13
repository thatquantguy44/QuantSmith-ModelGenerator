# Collateral Settlement Failure Propagation
**ID:** QMG-20261112-06 · **Priority:** 92/100 · **Phase:** not started.

## Problem and value
A failed transfer can block related collateral deliveries and financing obligations.

**Business decision:** target the settlement legs whose failure causes the most downstream loss. **Hypothesis:** Network preventive routing reduces aggregate failed obligations relative to isolated fail scoring.

## Formulation
```text
ExpectedLoss(G,action) versus ExpectedLoss(G minus failed edges,action)
```

**Data:** Dependency-linked settlement legs, legal routes, timestamps, collateral and failed instructions. **Baseline:** FIFO escalation by individual settlement. **Candidate:** directed graph contagion replay. **Advanced:** stochastic hypergraph scheduling and recovery routing. **Metrics:** cascade size, failed notional, recovery time and funding cost. **Key risk:** incomplete external dependencies and cross-entity visibility.

**Implementation:** networkx,simpy,ortools proposed; difficulty and capacity to be assessed. **Illustrative ROI hypothesis:** 2–4×, not a measured return.

## Research files
[Specification](SPEC.md) · [Plan](PLAN.md) · [Tasks](TASKS.md) · [Roadmap](ROADMAP.md) · [Handoff](HANDOFF.md) · [Sources](SOURCES.md) · [Evaluation](EVALS.md)

## AI and reuse files
[Agent](AGENT.md) · [Skill](SKILL.md) · [Prompt](PROMPT.md) · [Tooling](TOOLING.md) · [Workflow](WORKFLOW.md) · [Runtime](RUNTIME.md)

No model, historical result, source-specific licensing, or claimed publication has been verified.
