# ROADMAP — European Interconnector Congestion Power-Spread State Estimator
**No implementation started. Milestones are planning assumptions, not commitments.**

## Phase 0: rights and science gate (weeks 1–2)
Check ENTSO-E Transparency Platform File Library Guide, Oct 9 2026, US EIA Public API versus exact needed fields: ENTSO-E day-ahead prices, transfer capacities, interconnector outages, wind/load forecasts and contract liquidity. Verify calendar and rights. Reject unlicensed data.

## Phase 1: synthetic baseline (weeks 3–4)
Freeze math `Spread_{a,b,t}=Price_a,t-Price_b,t; Flow_{ab,t}≤ATC_{ab,t}; max_q E[q*Spread-CongestionCost(q)] with |q|≤AccessCap`, create deterministic fixtures and implement `Historical seasonal hourly spread by zone pair`. Gate AC-001 and AC-002.

## Phase 2: measured prototype (weeks 5–8)
Try `Physical-congestion regime HMM with capacity-constrained exposure mapper`, holdout on available historical timestamps and record Congestion regime Brier score, spread MAE, feasible net hedge carry and stress CVaR; compare non-parametric alternative and no-action.

## Phase 3: controlled shadow replay (weeks 9–12, if feasible)
Test Cross-zone transmission rights and operational capacities not freely tradable; timestamps and price revisions.; estimate actual execution Transmission rights/market access and collateral requirements dominate quoted spread opportunities., then decide Spread gains disappear after simultaneous public forecast access, congestion settlement and capacity rights..

## Phase 4: human decision
Independent quant/domain/legal reviewers validate. Annual benefit sensitivity $150k is **not** revenue; calculate business case only from audited data. Research can close as a negative result.
