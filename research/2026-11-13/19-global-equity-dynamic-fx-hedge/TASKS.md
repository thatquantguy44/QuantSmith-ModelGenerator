# TASKS — Dynamic Currency-Hedge and Rebalancing Tax for Global Equity
**Status:** All tasks TODO. Proposed test names are NOT run or present in code.

| ID | Task | Requirements | Concrete definition of done |
|---|---|---|---|
| T-001 | Verify market/legal permissions and rights to Country index total returns, currency spot/forward curves, FX liquidity, investability restrictions and funding rates. | REQ-001,NFR-002 | Signed accessible-source and action/market eligibility matrix |
| T-002 | Build immutable `global-equity-dynamic-fx-hedge` schema and synthetic fixtures at country equity market × FX forward tenor × monthly rebalance date | REQ-001,NFR-001,AC-001 | Future-vintage, duplicates and revisions rejected deterministically |
| T-003 | Implement 50% static currency hedges plus equal-risk country weights and quarterly turnover. with realistic frictions | REQ-002,AC-002 | Math, units, feasibility and no-trade unit tests green |
| T-004 | Implement initial Robust covariance and transaction-cost-aware FX hedge optimizer. | REQ-003,AC-003 | Pinned config, deterministic training, reproducible candidate outputs |
| T-005 | Design Distributionally robust conditional hedge allocation with Markov stress regime and partial hedging. ablation only if needed | REQ-003 | Incremental complexity budget versus simple candidate recorded |
| T-006 | Freeze chronological holdout and matched economic replay | REQ-004,NFR-001,AC-003 | Same action set; no post-decision information; execution cost included |
| T-007 | Evaluate after-cost drawdown, lower-tail CVaR, rolling correlation, FX hedge turnover and volatility.; stress Country index histories have vendor survivorship and free-float methodological changes; FX pricing may be unavailable at allocated size. | REQ-004,AC-004 | CI/stress metrics and fail/abstention report generated |
| T-008 | Review legal/data boundaries, stop/go and shadow plan | NFR-002,AC-005 | Explicit independent reviewer sign-off; no automatic deployment |

## Acceptance-test mapping (planned)
- AC-001 → `test_global_equity_dynamic_fx_hedge_asof`: sources unavailable at decision time must throw a typed error.
- AC-002 → `test_global_equity_dynamic_fx_hedge_baseline`: compare with hand-calculated synthetic examples.
- AC-003 → `test_global_equity_dynamic_fx_hedge_paired`: split embargo and matched action support.
- AC-004 → `test_global_equity_dynamic_fx_hedge_risk`: bounds, stress and cost sensitivity.
- AC-005 → `test_global_equity_dynamic_fx_hedge_public_gate`: confidential and unauthorized record rejection.

## Completion caveat
Only design documents exist. No test has been implemented or passed; DO NOT mark anything DONE until a verified run report and owner approval exists.
