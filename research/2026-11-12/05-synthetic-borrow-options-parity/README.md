# Synthetic Borrow Supply via Options Parity
**ID:** QMG-20261112-05 · **Priority:** 93/100 · **Phase:** not started.

## Problem and value
Physical borrow cost may diverge from implementable options/derivatives replication.

**Business decision:** choose physical versus synthetic financing exposure. **Hypothesis:** Parity-adjusted replication reduces funding cost for eligible positions after dividends and exercise risk.

## Formulation
```text
C-P≈S-PV(K)-PV(dividends)+borrow_adjustment; choose min total cost
```

**Data:** Options bid/ask, dividends, loan fees, stock price, funding, margin and assignment mechanics. **Baseline:** physical borrow only. **Candidate:** implied financing via corrected put-call parity. **Advanced:** mixed-integer derivative replication with exercise constraints. **Metrics:** executable financing benefit, hedge error, margin and basis risk. **Key risk:** American exercise and forecast-dividend mismatch.

**Implementation:** scipy,cvxpy,pandas proposed; difficulty and capacity to be assessed. **Illustrative ROI hypothesis:** 2–5×, not a measured return.

## Research files
[Specification](SPEC.md) · [Plan](PLAN.md) · [Tasks](TASKS.md) · [Roadmap](ROADMAP.md) · [Handoff](HANDOFF.md) · [Sources](SOURCES.md) · [Evaluation](EVALS.md)

## AI and reuse files
[Agent](AGENT.md) · [Skill](SKILL.md) · [Prompt](PROMPT.md) · [Tooling](TOOLING.md) · [Workflow](WORKFLOW.md) · [Runtime](RUNTIME.md)

No model, historical result, source-specific licensing, or claimed publication has been verified.
