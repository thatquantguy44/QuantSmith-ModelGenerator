# CFTC Positioning Concentration and Commodity Curve Convexity
**B · Domestic & global markets** · **Priority 91/100** · **Difficulty Medium** · **Feasibility: High for weekly strategy research** · **Publication interest 4/5 (conceptual, not a paper).**

## Why this exists
Speculator long/short crowding alone is a weak factor; crowding combined with curve convexity and roll liquidity may identify asymmetric liquidation windows.

**Market / geography:** United States commodity futures with global supply chains. **Asset classes:** energy, agricultural, metal futures term structures.

## Falsifiable hypothesis and investment/operational decision
CFTC public trader-category concentration interacts with futures curve slope/convexity to forecast downside tail asymmetry better than carry alone.

**Decision:** Scale futures trend/curve exposure after weekly public positioning releases with pre-set liquidation budgets..

## Research model
```text
Crowding_t=(spec_long_t-spec_short_t)/OI_t; Convexity_t=F1_t-2F2_t+F3_t; TailScore_t=β*Crowding_t*Convexity_t
```
F1..F3 are aligned futures maturities with explicit roll rules; OI is the reported futures open interest, all at publication availability.

## Data and decision clock
CFTC Disaggregated COT futures positions, futures contracts prices/rolls, EIA physical inventories where applicable. **Observation grain:** CFTC contract market × Tuesday reference position × Friday public release, then weekly trade clock. **Decision horizon:** earliest action is CFTC publication/next executable session; no use of Tuesday positions on Tuesday.

## Baseline versus candidate
- **Baseline:** Futures curve carry/roll-yield and 12-month time-series momentum.
- **Proposed model:** Positioning-conditioned conditional expected shortfall regression.
- **Advanced option:** Stochastic inventory-demand equilibrium with nonlinear dealer hedging and curve impact.
- **Primary metrics:** tail loss reduction, annualized Sharpe after roll/slippage, opportunity-cost drag and hedge stability.
- **Falsification:** Reject if tail-risk control does not beat carry/momentum or negative convexity effect changes sign in out-of-sample contracts.
- **Primary economic or methodological caveat:** CFTC taxonomy changes, combined report double-counting and slow publication may annihilate predictive edge.

## 24-month ROI sensitivity (unverified assumptions only)
USD $105k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $0k–$250k over 24 months. Net ROI = (gross benefit − cost)/cost = **-100% to 138%**. NOT forecast or historical measurement. Economic lever: hypothetical $20m risk budget, small tail-loss reduction in commodity futures over 24 months; benefits uncertain.

## Execution, capacity and feasibility
Enforce futures open interest participation cap, roll liquidity and margin stress; no physical commodity positions.

## Research documents
[SPEC](./SPEC.md) · [PLAN](./PLAN.md) · [TASKS](./TASKS.md) · [ROADMAP](./ROADMAP.md) · [HANDOFF](./HANDOFF.md) · [SOURCES](./SOURCES.md) · [EVALS](./EVALS.md)

## Reusable agent and engineering contracts
[AGENT](./AGENT.md) · [SKILL](./SKILL.md) · [PROMPT](./PROMPT.md) · [TOOLING](./TOOLING.md) · [WORKFLOW](./WORKFLOW.md) · [RUNTIME](./RUNTIME.md)

**Status: NOT STARTED.** These are specific scientific and engineering proposals, not executable deployments, experimental findings or empirically verified strategies.
