# Collateral Reuse Chain Stress Testing
**ID:** QMG-20261112-12 · **Priority:** 86/100 · **Phase:** not started.

## Problem and value
Legal reuse increases effective capacity but creates hidden dependence on settlement and margin links.

**Business decision:** set buffers and resilience policies for eligible collateral transformation chains. **Hypothesis:** Provenance-aware reuse graph explains stress contractions beyond gross reused collateral.

## Formulation
```text
I_effective=(Identity-A)^-1 I_base when spectral_radius(A)<1
```

**Data:** Source provenance, permissioned reuse contracts, collateral movements, haircut and margin events. **Baseline:** gross collateral stock and static stress. **Candidate:** legal reuse network input-output simulation. **Advanced:** dynamic network cascades with haircuts and intraday liquidity. **Metrics:** capacity contraction, margin calls, recovery time and chain failure. **Key risk:** double counting and unsupported rehypothecation rights.

**Implementation:** networkx,scipy.sparse,simpy proposed; difficulty and capacity to be assessed. **Illustrative ROI hypothesis:** 1–4×, not a measured return.

## Research files
[Specification](SPEC.md) · [Plan](PLAN.md) · [Tasks](TASKS.md) · [Roadmap](ROADMAP.md) · [Handoff](HANDOFF.md) · [Sources](SOURCES.md) · [Evaluation](EVALS.md)

## AI and reuse files
[Agent](AGENT.md) · [Skill](SKILL.md) · [Prompt](PROMPT.md) · [Tooling](TOOLING.md) · [Workflow](WORKFLOW.md) · [Runtime](RUNTIME.md)

No model, historical result, source-specific licensing, or claimed publication has been verified.
