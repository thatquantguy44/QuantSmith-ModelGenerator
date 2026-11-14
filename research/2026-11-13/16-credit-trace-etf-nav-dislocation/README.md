# Corporate-Bond TRACE Liquidity-to-ETF NAV Stress Transmission
**B · Domestic & global markets** · **Priority 90/100** · **Difficulty High** · **Feasibility: Medium requiring licensing** · **Publication interest 5/5 (conceptual, not a paper).**

## Why this exists
Bond ETF price-to-NAV discounts may reflect executable underlying liquidity, valuation lag, or hedging demand; naive discounts are not free arbitrage.

**Market / geography:** United States investment-grade/high-yield credit; optional Europe comparison. **Asset classes:** US corporate bonds, credit ETFs, basis risk.

## Falsifiable hypothesis and investment/operational decision
Publication-time TRACE liquidity dispersion predicts subsequent ETF tracking instability beyond ETF realized volatility and HY/IG spread levels.

**Decision:** Hedge credit ETF risk in periods of underlying bond liquidity deterioration without assuming stale NAV is executable..

## Research model
```text
LiquidityDisp_t=Q90(trade_cost_bond,t)-Q10(trade_cost_bond,t); predict |ETFprice_t-NAVestimate_t| with quote-timing controls
```
trade_cost_bond is valid time-matched cost proxy; NAVestimate is vendor methodology-specific, potentially stale and never treated as fillable.

## Data and decision clock
FINRA TRACE public aggregate/trade pages, subscription historical bond records, ETF market prices, NAV timestamps, bond indices, CDX basis. **Observation grain:** bond × disseminated trade timestamp × ETF NAV publication timestamp. **Decision horizon:** end-of-session / next-session ETF risk adjustment only; public aggregate data may not cover security-level historical panel.

## Baseline versus candidate
- **Baseline:** ETF realized volatility and quoted bid-ask spread.
- **Proposed model:** Robust bond-liquidity dispersion index and ETF tracking-state model.
- **Advanced option:** Structural ETF redemption/creation network with dealer intermediation bottlenecks.
- **Primary metrics:** tracking error forecast, credit tail loss, hedge slippage, redemption-state calibration.
- **Falsification:** Reject if no incremental tracking error forecast or lower stress drawdown after NAV timestamp normalization and realistic ETF costs.
- **Primary economic or methodological caveat:** Reported bond prices may be size-capped/delayed; TRACE trade access/licensing varies and NAV can embed stale marks.

## 24-month ROI sensitivity (unverified assumptions only)
USD $215k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $0k–$455k over 24 months. Net ROI = (gross benefit − cost)/cost = **-100% to 112%**. NOT forecast or historical measurement. Economic lever: hypothetical $20m credit hedge program, saving a fraction of tracking-loss during rare liquidity events; no realized estimate.

## Execution, capacity and feasibility
Only liquid ETFs and hedges, no synthetic bond execution assuming NAV arbitrage.

## Research documents
[SPEC](./SPEC.md) · [PLAN](./PLAN.md) · [TASKS](./TASKS.md) · [ROADMAP](./ROADMAP.md) · [HANDOFF](./HANDOFF.md) · [SOURCES](./SOURCES.md) · [EVALS](./EVALS.md)

## Reusable agent and engineering contracts
[AGENT](./AGENT.md) · [SKILL](./SKILL.md) · [PROMPT](./PROMPT.md) · [TOOLING](./TOOLING.md) · [WORKFLOW](./WORKFLOW.md) · [RUNTIME](./RUNTIME.md)

**Status: NOT STARTED.** These are specific scientific and engineering proposals, not executable deployments, experimental findings or empirically verified strategies.
