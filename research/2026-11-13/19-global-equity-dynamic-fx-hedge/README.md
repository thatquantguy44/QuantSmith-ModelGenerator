# Dynamic Currency-Hedge and Rebalancing Tax for Global Equity
**B · Domestic & global markets** · **Priority 87/100** · **Difficulty Medium** · **Feasibility: High with licensed index returns** · **Publication interest 4/5 (conceptual, not a paper).**

## Why this exists
Static FX hedges can overpay forward carry, turnover and correlation opportunity costs when equity/FX correlations flip across stress regimes.

**Market / geography:** US, Japan, euro area, UK and selected liquid EM equity markets. **Asset classes:** global equities and currency hedges.

## Falsifiable hypothesis and investment/operational decision
State-adaptive hedging reduces after-cost drawdown without sacrificing a pre-specified return floor relative to 0%, 50% and 100% static hedges.

**Decision:** Allocate country equity exposures and currency forward hedge ratios jointly under leverage, country, counterparty and capital-control constraints..

## Research model
```text
min_(w,h) E[(R_equity(w)+R_FX(w,h)-target)^2] + λ*ES_95 + μ*turnover(w,h); 0≤h_c≤hmax_c
```
w are country equity weights; h_c hedge fractions; ES_95 is expected shortfall; forward carry and bid/ask are charged at actual roll.

## Data and decision clock
Country index total returns, currency spot/forward curves, FX liquidity, investability restrictions and funding rates. **Observation grain:** country equity market × FX forward tenor × monthly rebalance date. **Decision horizon:** rebalance at scheduled month-end using prior-close prices and then-available forward quotes.

## Baseline versus candidate
- **Baseline:** 50% static currency hedges plus equal-risk country weights and quarterly turnover.
- **Proposed model:** Robust covariance and transaction-cost-aware FX hedge optimizer.
- **Advanced option:** Distributionally robust conditional hedge allocation with Markov stress regime and partial hedging.
- **Primary metrics:** after-cost drawdown, lower-tail CVaR, rolling correlation, FX hedge turnover and volatility.
- **Falsification:** Reject if lower-tail risk not improved by at least 5% net of forward carry and turnover without violating return floor.
- **Primary economic or methodological caveat:** Country index histories have vendor survivorship and free-float methodological changes; FX pricing may be unavailable at allocated size.

## 24-month ROI sensitivity (unverified assumptions only)
USD $135k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $20k–$270k over 24 months. Net ROI = (gross benefit − cost)/cost = **-85% to 100%**. NOT forecast or historical measurement. Economic lever: hypothetical $30m equity exposure; 0–42 bps annually saved from hedge inefficiency and drawdown control; weak scenario still pays some operational value.

## Execution, capacity and feasibility
Limit to index futures/ETFs and deliverable/non-deliverable forward liquidity; enforce market access and capital controls.

## Research documents
[SPEC](./SPEC.md) · [PLAN](./PLAN.md) · [TASKS](./TASKS.md) · [ROADMAP](./ROADMAP.md) · [HANDOFF](./HANDOFF.md) · [SOURCES](./SOURCES.md) · [EVALS](./EVALS.md)

## Reusable agent and engineering contracts
[AGENT](./AGENT.md) · [SKILL](./SKILL.md) · [PROMPT](./PROMPT.md) · [TOOLING](./TOOLING.md) · [WORKFLOW](./WORKFLOW.md) · [RUNTIME](./RUNTIME.md)

**Status: NOT STARTED.** These are specific scientific and engineering proposals, not executable deployments, experimental findings or empirically verified strategies.
