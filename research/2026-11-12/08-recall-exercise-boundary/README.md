# Loan Recall Early-Exercise Boundary
**ID:** QMG-20261112-08 · **Priority:** 90/100 · **Phase:** not started.

## Problem and value
Loans can end early due to governance, sale or liquidity rights that constrain inventory.

**Business decision:** forecast compliant beneficial-owner recall exercise and source replacement. **Hypothesis:** Owner-specific early-exercise states predict recall timing and lower replacement exposure.

## Formulation
```text
V_t=max(V_recall,t, E_t[carry_t+discount×V_t+1])
```

**Data:** Loan age, fee, recalls, corporate action calendar, owner restrictions, replacement cost. **Baseline:** constant owner-specific recall probability. **Candidate:** constrained survival and stopping model. **Advanced:** least-squares Monte Carlo owner exercise policy. **Metrics:** recall warning, replacement cost, calibration and fail prevention. **Key risk:** governance and fiduciary rights cannot be traded away.

**Implementation:** lifelines,numpy,scipy proposed; difficulty and capacity to be assessed. **Illustrative ROI hypothesis:** 2–4×, not a measured return.

## Research files
[Specification](SPEC.md) · [Plan](PLAN.md) · [Tasks](TASKS.md) · [Roadmap](ROADMAP.md) · [Handoff](HANDOFF.md) · [Sources](SOURCES.md) · [Evaluation](EVALS.md)

## AI and reuse files
[Agent](AGENT.md) · [Skill](SKILL.md) · [Prompt](PROMPT.md) · [Tooling](TOOLING.md) · [Workflow](WORKFLOW.md) · [Runtime](RUNTIME.md)

No model, historical result, source-specific licensing, or claimed publication has been verified.
