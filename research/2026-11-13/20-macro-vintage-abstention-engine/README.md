# Macro-Vintage Integrity Engine with Prediction Abstention
**B · Domestic & global markets** · **Priority 86/100** · **Difficulty Medium** · **Feasibility: Very high for data pipeline prototype** · **Publication interest 5/5 (conceptual, not a paper).**

## Why this exists
Most macro backtests silently use revised values and revised seasonal adjustments; an ML model may score highly on information that did not exist at decision time.

**Market / geography:** United States, euro area and OECD countries. **Asset classes:** global macro indicators, portfolio risk signals.

## Falsifiable hypothesis and investment/operational decision
A vintage-aware abstention gate reduces false active signals and revisional backtest overstatement versus always-on macro factor models.

**Decision:** Permit or abstain from a macro risk-signal update based on measured vintage quality, published delays and expected decision value..

## Research model
```text
Trade_t=1{E[utility(signal_t)|vintage_quality_t] > cost_t and quality_t>=q_min}; otherwise hold benchmark
```
quality measures source reliability, revision uncertainty, coverage and release history; expected utility estimated strictly from past vintages.

## Data and decision clock
ALFRED historical revisions, ECB yield releases, OECD SDMX data vintage calendars, US/global market proxies. **Observation grain:** economic indicator × observation period × release date × vintage ID. **Decision horizon:** update only after first verified public release; revisions must enter as new events, not retroactively.

## Baseline versus candidate
- **Baseline:** Always-on macro momentum score built from latest-vintage series.
- **Proposed model:** As-of macro feature store with release-confidence model and abstention.
- **Advanced option:** Bayesian missing-data multiple-vintage filtering and conformal selective prediction with capacity-aware portfolio overlay.
- **Primary metrics:** revision-induced backtest bias, selective risk loss, coverage, false alarm rate, time-to-data-availability.
- **Falsification:** Reject if abstention fails to reduce loss on corrected vintage history or simply abstains from all market decisions.
- **Primary economic or methodological caveat:** ALFRED historical series coverage, future revisions and OECD methodological breaks can be incomplete; abstention selection bias.

## 24-month ROI sensitivity (unverified assumptions only)
USD $130k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $20k–$245k over 24 months. Net ROI = (gross benefit − cost)/cost = **-85% to 88%**. NOT forecast or historical measurement. Economic lever: scenario: reduce failed model deployment and wasted model-validation hours, plus any trading uplift; 24-month benefits unmeasured.

## Execution, capacity and feasibility
Primarily a reusable research data-quality service; alpha/executable returns need licensed market backtest.

## Research documents
[SPEC](./SPEC.md) · [PLAN](./PLAN.md) · [TASKS](./TASKS.md) · [ROADMAP](./ROADMAP.md) · [HANDOFF](./HANDOFF.md) · [SOURCES](./SOURCES.md) · [EVALS](./EVALS.md)

## Reusable agent and engineering contracts
[AGENT](./AGENT.md) · [SKILL](./SKILL.md) · [PROMPT](./PROMPT.md) · [TOOLING](./TOOLING.md) · [WORKFLOW](./WORKFLOW.md) · [RUNTIME](./RUNTIME.md)

**Status: NOT STARTED.** These are specific scientific and engineering proposals, not executable deployments, experimental findings or empirically verified strategies.
