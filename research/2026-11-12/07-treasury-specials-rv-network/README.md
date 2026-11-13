# Treasury Specials Relative-Value Network
**ID:** QMG-20261112-07 · **Priority:** 91/100 · **Phase:** not started.

## Problem and value
CUSIP-level specials reflect issuance, deliverability and hedging demand beyond generic collateral rates.

**Business decision:** identify executable repo RV across related Treasury CUSIPs. **Hypothesis:** A supply-aware graph explains and monetizes relative scarcity after full trading costs.

## Formulation
```text
special_i=r_GC-r_repo_i; RV_ij=special_i-β_ij special_j
```

**Data:** CUSIP-level repo and general-collateral rates, SOMA auctions, supply, futures basket, fails. **Baseline:** historical CUSIP z-score of specials. **Candidate:** CUSIP graph, cointegration and structural event controls. **Advanced:** dynamic security-specific financing equilibrium. **Metrics:** net spread convergence, realized returns, capital and fail risk. **Key risk:** public SOMA cannot substitute for executable CUSIP quotes.

**Implementation:** pandas,statsmodels,networkx proposed; difficulty and capacity to be assessed. **Illustrative ROI hypothesis:** 2–4×, not a measured return.

## Research files
[Specification](SPEC.md) · [Plan](PLAN.md) · [Tasks](TASKS.md) · [Roadmap](ROADMAP.md) · [Handoff](HANDOFF.md) · [Sources](SOURCES.md) · [Evaluation](EVALS.md)

## AI and reuse files
[Agent](AGENT.md) · [Skill](SKILL.md) · [Prompt](PROMPT.md) · [Tooling](TOOLING.md) · [Workflow](WORKFLOW.md) · [Runtime](RUNTIME.md)

No model, historical result, source-specific licensing, or claimed publication has been verified.
