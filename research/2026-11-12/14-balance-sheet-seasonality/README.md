# Balance-Sheet Seasonality Arbitrage
**ID:** QMG-20261112-14 · **Priority:** 84/100 · **Phase:** not started.

## Problem and value
Calendar events create predictable seasonal changes in constrained funding supply.

**Business decision:** choose funding tenor and capacity reserves around reporting dates. **Hypothesis:** Calendar-aware funding reduces ex-ante cost on unseen quarter-ends after realistic balance-sheet charges.

## Formulation
```text
max Σ_t [financing revenue_t-funding_t-λ_t×capacity_t] under capacity limits
```

**Data:** Repo spread term structure, settlement calendar, quarter-end dates, financing usage. **Baseline:** constant overnight-roll financing. **Candidate:** calendar event study with capacity-aware optimization. **Advanced:** stochastic dynamic capacity control under regime variation. **Metrics:** holdout funding cost, stress liquidity, rollover risk and drawdown. **Key risk:** well-known quarter-end effects may already be fully priced.

**Implementation:** pandas,statsmodels,cvxpy proposed; difficulty and capacity to be assessed. **Illustrative ROI hypothesis:** 2–4×, not a measured return.

## Research files
[Specification](SPEC.md) · [Plan](PLAN.md) · [Tasks](TASKS.md) · [Roadmap](ROADMAP.md) · [Handoff](HANDOFF.md) · [Sources](SOURCES.md) · [Evaluation](EVALS.md)

## AI and reuse files
[Agent](AGENT.md) · [Skill](SKILL.md) · [Prompt](PROMPT.md) · [Tooling](TOOLING.md) · [Workflow](WORKFLOW.md) · [Runtime](RUNTIME.md)

No model, historical result, source-specific licensing, or claimed publication has been verified.
