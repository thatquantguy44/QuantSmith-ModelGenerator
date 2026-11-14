# AI Infrastructure Capex-to-Power-and-Export Supply Chain Factor
**B · Domestic & global markets** · **Priority 92/100** · **Difficulty High** · **Feasibility: Medium** · **Publication interest 5/5 (conceptual, not a paper).**

## Why this exists
Corporate capex plans for AI facilities may not translate into actual compute deployments until grids, transformers, electric generation and overseas component exports clear physical bottlenecks.

**Market / geography:** United States, Taiwan, South Korea, Singapore and Malaysia. **Asset classes:** equity sectors, electricity demand, industrial exports.

## Falsifiable hypothesis and investment/operational decision
Public capex-to-power-to-export bottleneck signals predict medium-horizon revisions across semiconductor equipment, utilities and data-center supply chains.

**Decision:** Construct capacity-confirmation exposures instead of mechanically buying companies mentioning AI investment..

## Research model
```text
Bottleneck_t = min(grid_capacity_t/expected_load_t, export_supply_t/needed_components_t); signal_i,t=exposure_i*(Bottleneck_t-1)
```
expected_load and needed_components are explicit assumptions, not observable facts; no inferral of private company data-center locations.

## Data and decision clock
SEC EDGAR filed capital expenditure and commitments, EIA power demand/generation, public utility service-area reports, UN Comtrade semiconductor/electrical equipment trade. **Observation grain:** public company disclosure × filing-time vintage × geography × monthly energy/trade release. **Decision horizon:** rebalance monthly after latest public filings, energy updates and international trade release.

## Baseline versus candidate
- **Baseline:** Equal-weight US tech/utility/semiconductor thematic basket with broad market hedge.
- **Proposed model:** Supply-chain bottleneck score anchored in publicly observed physical constraints.
- **Advanced option:** Bayesian uncertainty propagation across disclosed commitments, supply chains and commodity/electricity capacity.
- **Primary metrics:** sector-neutral residual return, realized earnings revision, stock/industry turnover and capacity sensitivity.
- **Falsification:** Reject if holdout earnings-revision association and after-cost portfolio uplift vanish after mega-cap momentum controls.
- **Primary economic or methodological caveat:** Disclosure boilerplate, future guidance and partial energy-grid footprint can generate strong hindsight mapping bias.

## 24-month ROI sensitivity (unverified assumptions only)
USD $180k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $0k–$560k over 24 months. Net ROI = (gross benefit − cost)/cost = **-100% to 211%**. NOT forecast or historical measurement. Economic lever: hypothetical $15m thematic sleeve; 0–185 bps annualized incremental after-cost return within favorable scenario; zero benefit base case.

## Execution, capacity and feasibility
Cap exposure to liquid industry ETFs/stocks; forecast vintages and reasonable turnover restrictions.

## Research documents
[SPEC](./SPEC.md) · [PLAN](./PLAN.md) · [TASKS](./TASKS.md) · [ROADMAP](./ROADMAP.md) · [HANDOFF](./HANDOFF.md) · [SOURCES](./SOURCES.md) · [EVALS](./EVALS.md)

## Reusable agent and engineering contracts
[AGENT](./AGENT.md) · [SKILL](./SKILL.md) · [PROMPT](./PROMPT.md) · [TOOLING](./TOOLING.md) · [WORKFLOW](./WORKFLOW.md) · [RUNTIME](./RUNTIME.md)

**Status: NOT STARTED.** These are specific scientific and engineering proposals, not executable deployments, experimental findings or empirically verified strategies.
