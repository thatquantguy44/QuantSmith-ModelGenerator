# Repo Term Structure Dislocation Engine
**ID:** QMG-20261112-02 · **Priority:** 96/100 · **Phase:** not started.

## Problem and value
Observed term repo spreads incorporate collateral scarcity and balance-sheet constraints besides expected overnight rates.

**Business decision:** choose term financing maturity and collateral route. **Hypothesis:** A collateral-aware funding curve beats overnight rolling after executable financing costs.

## Formulation
```text
Basis(T)=r_repo(T)-T^-1∫E_t[r_ON(u)]du-collateral_carry(T)
```

**Data:** Repo rate/tenor quotes, SOFR, collateral CUSIP, haircut, balance-sheet dates. **Baseline:** overnight funding rollover. **Candidate:** security-aware no-arbitrage term curve. **Advanced:** regime-switching state-space financing optimization. **Metrics:** after-cost funding savings, basis convergence, risk and drawdown. **Key risk:** indicative prices and bid/ask execution mismatch.

**Implementation:** numpy,statsmodels,cvxpy proposed; difficulty and capacity to be assessed. **Illustrative ROI hypothesis:** 2–5×, not a measured return.

## Research files
[Specification](SPEC.md) · [Plan](PLAN.md) · [Tasks](TASKS.md) · [Roadmap](ROADMAP.md) · [Handoff](HANDOFF.md) · [Sources](SOURCES.md) · [Evaluation](EVALS.md)

## AI and reuse files
[Agent](AGENT.md) · [Skill](SKILL.md) · [Prompt](PROMPT.md) · [Tooling](TOOLING.md) · [Workflow](WORKFLOW.md) · [Runtime](RUNTIME.md)

No model, historical result, source-specific licensing, or claimed publication has been verified.
