# TASKS — Treasury Clearing Access-Path & Duplicate-Margin Optimizer
**Status:** All tasks TODO. Proposed test names are NOT run or present in code.

| ID | Task | Requirements | Concrete definition of done |
|---|---|---|---|
| T-001 | Verify market/legal permissions and rights to Eligible trade templates; path availability; historical quote spreads; initial/variation margin stress; capital/CCLF allocation; modeled netting sets; direct/sponsored/agent fees. | REQ-001,NFR-002 | Signed accessible-source and action/market eligibility matrix |
| T-002 | Build immutable `clearing-access-duplicate-margin` schema and synthetic fixtures at trade × eligible clearing access path × decision timestamp | REQ-001,NFR-001,AC-001 | Future-vintage, duplicates and revisions rejected deterministically |
| T-003 | Implement Minimize executable repo rate ignoring path-specific costs, after validating that every route is eligible. with realistic frictions | REQ-002,AC-002 | Math, units, feasibility and no-trade unit tests green |
| T-004 | Implement initial Mixed-integer convex routing with separate margin, settlement and liquidity shadow prices. | REQ-003,AC-003 | Pinned config, deterministic training, reproducible candidate outputs |
| T-005 | Design Stochastic two-stage CCP-margin and default-fund planning with cross-netting robustness. ablation only if needed | REQ-003 | Incremental complexity budget versus simple candidate recorded |
| T-006 | Freeze chronological holdout and matched economic replay | REQ-004,NFR-001,AC-003 | Same action set; no post-decision information; execution cost included |
| T-007 | Evaluate USD all-in funding cost, dollar liquidity encumbrance, margin stress p99, ineligible route count, rejection rate.; stress Clearing rule exemptions and netting eligibility vary; estimated margin offsets could be nonportable across entities. | REQ-004,AC-004 | CI/stress metrics and fail/abstention report generated |
| T-008 | Review legal/data boundaries, stop/go and shadow plan | NFR-002,AC-005 | Explicit independent reviewer sign-off; no automatic deployment |

## Acceptance-test mapping (planned)
- AC-001 → `test_clearing_access_duplicate_margin_asof`: sources unavailable at decision time must throw a typed error.
- AC-002 → `test_clearing_access_duplicate_margin_baseline`: compare with hand-calculated synthetic examples.
- AC-003 → `test_clearing_access_duplicate_margin_paired`: split embargo and matched action support.
- AC-004 → `test_clearing_access_duplicate_margin_risk`: bounds, stress and cost sensitivity.
- AC-005 → `test_clearing_access_duplicate_margin_public_gate`: confidential and unauthorized record rejection.

## Completion caveat
Only design documents exist. No test has been implemented or passed; DO NOT mark anything DONE until a verified run report and owner approval exists.
