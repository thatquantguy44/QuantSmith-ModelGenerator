# Treasury Issuance-to-Dealer Intermediation Capacity Map
**A · Securities finance** · **Priority 87/100** · **Difficulty Medium** · **Feasibility: High for public surveillance** · **Publication interest 5/5 (conceptual, not a paper).**

## Why this exists
New issuance and benchmark rollovers impose inventory absorption on dealer balance sheets; public positioning snapshots may reveal when the marginal intermediation cost rises.

**Market / geography:** United States issuance and dealer system. **Asset classes:** Treasuries, dealer positions and financing.

## Falsifiable hypothesis and investment/operational decision
Public auction-supply and weekly dealer-position innovations predict future Treasury liquidity stress more reliably than rate volatility alone.

**Decision:** Set research-level short-term Treasury liquidity stress overlays around security supply events, independent of day-of-quarter calendar effects..

## Research model
```text
C_t=Δissuance_t - β*Δdealer_financed_positions_t; p_(t+h)=sigmoid(α+γ*C_(available≤t)+δ*vol_t)
```
C_t is an issuance-absorption mismatch proxy, not observed dealer capital; p is stress probability, h is pre-set future horizon.

## Data and decision clock
Treasury auction issuance and settlement schedule; weekly primary dealer net positions/financing; OFR repo aggregates; public Treasury yield changes. **Observation grain:** issuance cohort × week of publicly released dealer aggregates. **Decision horizon:** weekly close after primary dealer publication; never treat reported prior-week positions as contemporaneous.

## Baseline versus candidate
- **Baseline:** Treasury yield volatility and calendar week indicators.
- **Proposed model:** Event-study + state-space dealer supply absorption proxy.
- **Advanced option:** Instrumented quasi-experiment using prescheduled auction supply shocks and cross-CUSIP constraints.
- **Primary metrics:** stress forecast Brier, AUPRC, lead-time, false positives and hedge drawdown.
- **Falsification:** Reject if no improvement over the rate-volatility-only benchmark on genuinely held-out issuance regimes.
- **Primary economic or methodological caveat:** Aggregate dealer reports cannot identify securities or dealers and issuance is endogenous to financing conditions.

## 24-month ROI sensitivity (unverified assumptions only)
USD $100k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $25k–$170k over 24 months. Net ROI = (gross benefit − cost)/cost = **-75% to 70%**. NOT forecast or historical measurement. Economic lever: scenario: one avoided bad inventory allocation month or improved hedging stress alerts; not a measured signal.

## Execution, capacity and feasibility
Public signal is a risk overlay; tradability needs actual Treasury order book, bid/ask, duration and repo access.

## Research documents
[SPEC](./SPEC.md) · [PLAN](./PLAN.md) · [TASKS](./TASKS.md) · [ROADMAP](./ROADMAP.md) · [HANDOFF](./HANDOFF.md) · [SOURCES](./SOURCES.md) · [EVALS](./EVALS.md)

## Reusable agent and engineering contracts
[AGENT](./AGENT.md) · [SKILL](./SKILL.md) · [PROMPT](./PROMPT.md) · [TOOLING](./TOOLING.md) · [WORKFLOW](./WORKFLOW.md) · [RUNTIME](./RUNTIME.md)

**Status: NOT STARTED.** These are specific scientific and engineering proposals, not executable deployments, experimental findings or empirically verified strategies.
