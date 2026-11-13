# Optimal Financing Research Experiment Design
**ID:** QMG-20261112-15 · **Priority:** 83/100 · **Phase:** not started.

## Problem and value
Quant teams spend constrained time on uncertain ideas without common decision-value criteria.

**Business decision:** allocate scarce research effort to high information-value experiments. **Hypothesis:** Expected value of sample information improves go/no-go efficiency over equal research budgets.

## Formulation
```text
experiment*=argmax_e{E[max_a Value(a)|new information_e]-max_a E[Value(a)]-Cost(e)}
```

**Data:** Experiment budgets, model alternatives, synthetic case studies, past evidence quality and reproducibility logs. **Baseline:** equal effort per idea. **Candidate:** Bayesian value-of-information and sequential experiment selection. **Advanced:** knowledge-gradient portfolio policy with correlated research tasks. **Metrics:** decision value per research hour, false discovery, stopping time and deployed value. **Key risk:** retrospective outcomes are selectively recorded and success probabilities subjective.

**Implementation:** numpy,pymc,optuna,scipy proposed; difficulty and capacity to be assessed. **Illustrative ROI hypothesis:** 2–5×, not a measured return.

## Research files
[Specification](SPEC.md) · [Plan](PLAN.md) · [Tasks](TASKS.md) · [Roadmap](ROADMAP.md) · [Handoff](HANDOFF.md) · [Sources](SOURCES.md) · [Evaluation](EVALS.md)

## AI and reuse files
[Agent](AGENT.md) · [Skill](SKILL.md) · [Prompt](PROMPT.md) · [Tooling](TOOLING.md) · [Workflow](WORKFLOW.md) · [Runtime](RUNTIME.md)

No model, historical result, source-specific licensing, or claimed publication has been verified.
