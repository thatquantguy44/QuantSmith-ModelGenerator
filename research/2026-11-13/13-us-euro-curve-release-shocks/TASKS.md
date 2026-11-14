# TASKS — US–Euro Sovereign Curve Shock Decomposition with Data Vintages
**Status:** All tasks TODO. Proposed test names are NOT run or present in code.

| ID | Task | Requirements | Concrete definition of done |
|---|---|---|---|
| T-001 | Verify market/legal permissions and rights to ECB published euro yield curve, US yields and ALFRED macro vintages, official release times, FX hedges, rates futures cost. | REQ-001,NFR-002 | Signed accessible-source and action/market eligibility matrix |
| T-002 | Build immutable `us-euro-curve-release-shocks` schema and synthetic fixtures at economic release event × curve tenor × publication instant × geography | REQ-001,NFR-001,AC-001 | Future-vintage, duplicates and revisions rejected deterministically |
| T-003 | Implement 60-day rolling DV01-neutral cross-market beta hedge. with realistic frictions | REQ-002,AC-002 | Math, units, feasibility and no-trade unit tests green |
| T-004 | Implement initial Vintaged announcement factor model plus shrinkage hedge weights. | REQ-003,AC-003 | Pinned config, deterministic training, reproducible candidate outputs |
| T-005 | Design Hierarchical structural yield-curve state-space with distinct real-rate and term-premium factor loading. ablation only if needed | REQ-003 | Incremental complexity budget versus simple candidate recorded |
| T-006 | Freeze chronological holdout and matched economic replay | REQ-004,NFR-001,AC-003 | Same action set; no post-decision information; execution cost included |
| T-007 | Evaluate OOS hedging variance reduction, implementation shortfall, tail DV01 loss, signal turnover.; stress Public releases cannot recreate market consensus surprises without a licensed historical consensus dataset or explicit no-consensus baseline. | REQ-004,AC-004 | CI/stress metrics and fail/abstention report generated |
| T-008 | Review legal/data boundaries, stop/go and shadow plan | NFR-002,AC-005 | Explicit independent reviewer sign-off; no automatic deployment |

## Acceptance-test mapping (planned)
- AC-001 → `test_us_euro_curve_release_shocks_asof`: sources unavailable at decision time must throw a typed error.
- AC-002 → `test_us_euro_curve_release_shocks_baseline`: compare with hand-calculated synthetic examples.
- AC-003 → `test_us_euro_curve_release_shocks_paired`: split embargo and matched action support.
- AC-004 → `test_us_euro_curve_release_shocks_risk`: bounds, stress and cost sensitivity.
- AC-005 → `test_us_euro_curve_release_shocks_public_gate`: confidential and unauthorized record rejection.

## Completion caveat
Only design documents exist. No test has been implemented or passed; DO NOT mark anything DONE until a verified run report and owner approval exists.
