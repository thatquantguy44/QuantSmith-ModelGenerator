# Weather Forecast Revision as an Electricity-to-Gas Risk Hedge
**B · Domestic & global markets** · **Priority 89/100** · **Difficulty Medium-high** · **Feasibility: High public physical data, paid market execution** · **Publication interest 4/5 (conceptual, not a paper).**

## Why this exists
Weather surprises drive power demand, but using finalized observed weather in a historical strategy produces impossible lead-time and exaggerates energy trading edge.

**Market / geography:** US regional power markets and Henry Hub-linked energy. **Asset classes:** electricity load, natural gas, utilities and futures.

## Falsifiable hypothesis and investment/operational decision
Timestamped forecast *revisions* explain next-session electricity net-load stress better than absolute forecast temperature or seasonal normals.

**Decision:** Size gas/power-linked hedges using only prior-issued weather forecasts and expected net-load revisions..

## Research model
```text
Revision_r,t = LoadForecast_r,t^(latest issued) - LoadForecast_r,t^(prior issued); Hedge_t=clip(β*Revision_r,t,limits)
```
r is power balancing authority; revisions use two immutable issue-time snapshots; hedge maps only to liquid related assets with modeled cross-basis.

## Data and decision clock
NWS issued and archived forecasts, EIA balancing authority hourly load and generation, power/gas futures settlements and basis. **Observation grain:** balancing authority × weather forecast issuance × lead hour. **Decision horizon:** forecast issuance is the earliest legal decision; never consume later realized weather or EIA actual load before release.

## Baseline versus candidate
- **Baseline:** Seasonal degree-day demand regression and absolute temperature forecasts.
- **Proposed model:** Net-load forecast-revision elasticity with non-linear stress threshold.
- **Advanced option:** Probabilistic shortfall-and-constraint model with weather ensemble calibration.
- **Primary metrics:** load p95 quantile loss, probabilistic calibration, hedge tracking error, net futures carry.
- **Falsification:** Reject if no improvements in forecast quantile loss or hedge after-cost variance over degrees-day baseline.
- **Primary economic or methodological caveat:** Archive of *historical forecasts as issued* may be inaccessible; today's historical observations are not contemporaneous forecasts.

## 24-month ROI sensitivity (unverified assumptions only)
USD $170k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $0k–$470k over 24 months. Net ROI = (gross benefit − cost)/cost = **-100% to 176%**. NOT forecast or historical measurement. Economic lever: hypothetical $10m energy risk sleeve with 0–235 bps annualized risk/carry improvements; outcomes uncertain.

## Execution, capacity and feasibility
Trade via highly liquid gas futures or energy equity baskets, with geographic basis and sector beta mismatch priced.

## Research documents
[SPEC](./SPEC.md) · [PLAN](./PLAN.md) · [TASKS](./TASKS.md) · [ROADMAP](./ROADMAP.md) · [HANDOFF](./HANDOFF.md) · [SOURCES](./SOURCES.md) · [EVALS](./EVALS.md)

## Reusable agent and engineering contracts
[AGENT](./AGENT.md) · [SKILL](./SKILL.md) · [PROMPT](./PROMPT.md) · [TOOLING](./TOOLING.md) · [WORKFLOW](./WORKFLOW.md) · [RUNTIME](./RUNTIME.md)

**Status: NOT STARTED.** These are specific scientific and engineering proposals, not executable deployments, experimental findings or empirically verified strategies.
