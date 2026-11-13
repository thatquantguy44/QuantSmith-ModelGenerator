# Financing Execution Shortfall Model
**ID:** QMG-20261112-13 · **Priority:** 85/100 · **Phase:** not started.

## Problem and value
Pricing execution can deteriorate between request, quote, acceptance, booking and settlement.

**Business decision:** diagnose where quoted financing economics leak before completed settlement. **Hypothesis:** Point-in-time causal leakage attribution discovers correctable costs over a quote-only baseline.

## Formulation
```text
shortfall=realized_cost-decision_cost=market_move+delay+negotiation+settlement
```

**Data:** Timestamped RFQs, quotes, fill/rejects, booked fees, market moves and settlement. **Baseline:** executed spread minus indicative quote. **Candidate:** cost-inclusive execution shortfall event ledger. **Advanced:** matched counterfactual execution-policy evaluator. **Metrics:** bps slippage, recovered P&L, latency and fill rate. **Key risk:** quotes may be non-executable; client selection creates bias.

**Implementation:** polars,duckdb,statsmodels proposed; difficulty and capacity to be assessed. **Illustrative ROI hypothesis:** 2–4×, not a measured return.

## Research files
[Specification](SPEC.md) · [Plan](PLAN.md) · [Tasks](TASKS.md) · [Roadmap](ROADMAP.md) · [Handoff](HANDOFF.md) · [Sources](SOURCES.md) · [Evaluation](EVALS.md)

## AI and reuse files
[Agent](AGENT.md) · [Skill](SKILL.md) · [Prompt](PROMPT.md) · [Tooling](TOOLING.md) · [Workflow](WORKFLOW.md) · [Runtime](RUNTIME.md)

No model, historical result, source-specific licensing, or claimed publication has been verified.
