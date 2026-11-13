# Cross-Currency Repo Basis Optimization
**ID:** QMG-20261112-09 · **Priority:** 89/100 · **Phase:** not started.

## Problem and value
Different currency repo and FX swap combinations can create cost differences after all frictions.

**Business decision:** choose FX-hedged financing currency and legal collateral path. **Hypothesis:** CIP-adjusted multi-currency routing beats domestic-only financing where transferable collateral exists.

## Formulation
```text
USD-equivalent rate=foreign repo rate+FX hedge+basis+collateral/capital costs
```

**Data:** FX swaps, currencies, tenor rates, haircuts, FX settlements, taxes, legal eligibility. **Baseline:** domestic collateral and repo only. **Candidate:** covered-interest-parity-adjusted funding network. **Advanced:** stochastic multi-currency funding and collateral flow. **Metrics:** hedged carry, capacity, FX basis risk and all-in spread. **Key risk:** false arbitrage from stale asynchronous or inaccessible quotes.

**Implementation:** networkx,cvxpy,scipy proposed; difficulty and capacity to be assessed. **Illustrative ROI hypothesis:** 2–5×, not a measured return.

## Research files
[Specification](SPEC.md) · [Plan](PLAN.md) · [Tasks](TASKS.md) · [Roadmap](ROADMAP.md) · [Handoff](HANDOFF.md) · [Sources](SOURCES.md) · [Evaluation](EVALS.md)

## AI and reuse files
[Agent](AGENT.md) · [Skill](SKILL.md) · [Prompt](PROMPT.md) · [Tooling](TOOLING.md) · [Workflow](WORKFLOW.md) · [Runtime](RUNTIME.md)

No model, historical result, source-specific licensing, or claimed publication has been verified.
