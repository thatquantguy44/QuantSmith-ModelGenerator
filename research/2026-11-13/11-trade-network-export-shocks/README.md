# Trade-Network Export-Shock Transmission to Equity Sectors
**B · Domestic & global markets** · **Priority 96/100** · **Difficulty High** · **Feasibility: Medium-high with sector exposures** · **Publication interest 5/5 (conceptual, not a paper).**

## Why this exists
Changes in bilateral product-level exports are not evenly distributed: input-output bottlenecks may propagate to equity sectors before aggregate macro summaries appear.

**Market / geography:** US, Mexico, Germany, Japan, Korea, China and ASEAN markets. **Asset classes:** global equities and trade flows.

## Falsifiable hypothesis and investment/operational decision
Lag-aware product-network shocks identify medium-horizon cross-country sector earnings surprises beyond FX and industrial production.

**Decision:** Adjust public-market sector risk or hedges using time-valid trade-network concentration shocks, not a blunt GDP exposure factor..

## Research model
```text
Shock_(c,k,t)=Σ_p upstream_weight_(c,k,p)*Δexports_(p,t); alpha_(sector,t+h)=β*Shock_available_t - controls
```
c is country, k sector, p harmonized product/trade edge, h a preselected post-publication investment horizon.

## Data and decision clock
UN Comtrade reported and partner-reported trade by HS code/month; sector country revenue mix; FX; sector returns and macro controls. **Observation grain:** reporter × partner × HS code × reference month × publication/availability timestamp. **Decision horizon:** monthly after trade report publication and revision; NEVER trade at reference-month timestamp.

## Baseline versus candidate
- **Baseline:** Equal-weight country sector allocation with FX and local industrial production controls.
- **Proposed model:** Sparse directed trade graph factor with event-lag-aware regressions.
- **Advanced option:** Causal graph neural propagation with hard release-vintage masking and sector earnings transmission.
- **Primary metrics:** OOS sector information coefficient, dollar-neutral Sharpe, earnings revision hit rate, turnover and tail loss.
- **Falsification:** Reject if positive net cross-country IC is not stable in each of two disjoint geographic holdouts or after publication lags.
- **Primary economic or methodological caveat:** Revisions, late reporters, trade re-exports and mapping HS codes to listed firms can create survivorship and spurious exposure.

## 24-month ROI sensitivity (unverified assumptions only)
USD $150k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $0k–$520k over 24 months. Net ROI = (gross benefit − cost)/cost = **-100% to 247%**. NOT forecast or historical measurement. Economic lever: hypothetical $10m liquid sector sleeve and 0–260 bps gross annualized alpha capture over 2 years; zero base benefit is plausible.

## Execution, capacity and feasibility
ETFs and liquid futures only for first implementation; portfolio turnover caps and country exposure floors.

## Research documents
[SPEC](./SPEC.md) · [PLAN](./PLAN.md) · [TASKS](./TASKS.md) · [ROADMAP](./ROADMAP.md) · [HANDOFF](./HANDOFF.md) · [SOURCES](./SOURCES.md) · [EVALS](./EVALS.md)

## Reusable agent and engineering contracts
[AGENT](./AGENT.md) · [SKILL](./SKILL.md) · [PROMPT](./PROMPT.md) · [TOOLING](./TOOLING.md) · [WORKFLOW](./WORKFLOW.md) · [RUNTIME](./RUNTIME.md)

**Status: NOT STARTED.** These are specific scientific and engineering proposals, not executable deployments, experimental findings or empirically verified strategies.
