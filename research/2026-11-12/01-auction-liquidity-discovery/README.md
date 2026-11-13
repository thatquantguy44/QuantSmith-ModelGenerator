# Auction-Based Securities Lending Liquidity Discovery
**ID:** QMG-20261112-01 · **Priority:** 97/100 · **Phase:** not started.

## Problem and value
Only executed bilateral loan prices are observed; rejected locates censor willingness to pay.

**Business decision:** set fee and allocation for scarce lendable securities. **Hypothesis:** A structural auction policy improves net revenue over highest-fee-first after response and retention costs.

## Formulation
```text
max Σ_c ∫(v_c(u)-k_c(u))du subject to Σ_c q_c≤I
```

**Data:** Timestamped locate quotes, revisions, rejects, fills, quantities and source-specific inventory. **Baseline:** highest-fee-first feasible allocation. **Candidate:** censored structural demand + constrained auction. **Advanced:** hierarchical Bayesian mechanism design. **Metrics:** net revenue, allocative efficiency, fill rate, churn and regret. **Key risk:** censored demand, endogenous quote selection.

**Implementation:** scipy,cvxpy,pymc proposed; difficulty and capacity to be assessed. **Illustrative ROI hypothesis:** 3–6×, not a measured return.

## Research files
[Specification](SPEC.md) · [Plan](PLAN.md) · [Tasks](TASKS.md) · [Roadmap](ROADMAP.md) · [Handoff](HANDOFF.md) · [Sources](SOURCES.md) · [Evaluation](EVALS.md)

## AI and reuse files
[Agent](AGENT.md) · [Skill](SKILL.md) · [Prompt](PROMPT.md) · [Tooling](TOOLING.md) · [Workflow](WORKFLOW.md) · [Runtime](RUNTIME.md)

No model, historical result, source-specific licensing, or claimed publication has been verified.
