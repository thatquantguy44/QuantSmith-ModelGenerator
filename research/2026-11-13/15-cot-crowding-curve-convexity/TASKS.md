# TASKS — CFTC Positioning Concentration and Commodity Curve Convexity
**Status:** All tasks TODO. Proposed test names are NOT run or present in code.

| ID | Task | Requirements | Concrete definition of done |
|---|---|---|---|
| T-001 | Verify market/legal permissions and rights to CFTC Disaggregated COT futures positions, futures contracts prices/rolls, EIA physical inventories where applicable. | REQ-001,NFR-002 | Signed accessible-source and action/market eligibility matrix |
| T-002 | Build immutable `cot-crowding-curve-convexity` schema and synthetic fixtures at CFTC contract market × Tuesday reference position × Friday public release, then weekly trade clock | REQ-001,NFR-001,AC-001 | Future-vintage, duplicates and revisions rejected deterministically |
| T-003 | Implement Futures curve carry/roll-yield and 12-month time-series momentum. with realistic frictions | REQ-002,AC-002 | Math, units, feasibility and no-trade unit tests green |
| T-004 | Implement initial Positioning-conditioned conditional expected shortfall regression. | REQ-003,AC-003 | Pinned config, deterministic training, reproducible candidate outputs |
| T-005 | Design Stochastic inventory-demand equilibrium with nonlinear dealer hedging and curve impact. ablation only if needed | REQ-003 | Incremental complexity budget versus simple candidate recorded |
| T-006 | Freeze chronological holdout and matched economic replay | REQ-004,NFR-001,AC-003 | Same action set; no post-decision information; execution cost included |
| T-007 | Evaluate tail loss reduction, annualized Sharpe after roll/slippage, opportunity-cost drag and hedge stability.; stress CFTC taxonomy changes, combined report double-counting and slow publication may annihilate predictive edge. | REQ-004,AC-004 | CI/stress metrics and fail/abstention report generated |
| T-008 | Review legal/data boundaries, stop/go and shadow plan | NFR-002,AC-005 | Explicit independent reviewer sign-off; no automatic deployment |

## Acceptance-test mapping (planned)
- AC-001 → `test_cot_crowding_curve_convexity_asof`: sources unavailable at decision time must throw a typed error.
- AC-002 → `test_cot_crowding_curve_convexity_baseline`: compare with hand-calculated synthetic examples.
- AC-003 → `test_cot_crowding_curve_convexity_paired`: split embargo and matched action support.
- AC-004 → `test_cot_crowding_curve_convexity_risk`: bounds, stress and cost sensitivity.
- AC-005 → `test_cot_crowding_curve_convexity_public_gate`: confidential and unauthorized record rejection.

## Completion caveat
Only design documents exist. No test has been implemented or passed; DO NOT mark anything DONE until a verified run report and owner approval exists.
