# TASKS — Cash versus Noncash Loan-Collateral Economic Frontier
**Status:** All tasks TODO. Proposed test names are NOT run or present in code.

| ID | Task | Requirements | Concrete definition of done |
|---|---|---|---|
| T-001 | Verify market/legal permissions and rights to Cash and noncash terms, rebate schedules, reinvestment constraints, asset eligibility, mark-to-market, haircuts and legal restrictions. | REQ-001,NFR-002 | Signed accessible-source and action/market eligibility matrix |
| T-002 | Build immutable `cash-noncash-lending-collateral-frontier` schema and synthetic fixtures at loan offer × collateral type × owner mandate × quotation timestamp | REQ-001,NFR-001,AC-001 | Future-vintage, duplicates and revisions rejected deterministically |
| T-003 | Implement Choose the highest headline loan spread among eligible offers. with realistic frictions | REQ-002,AC-002 | Math, units, feasibility and no-trade unit tests green |
| T-004 | Implement initial Loan-specific all-in economic break-even and constraints solver. | REQ-003,AC-003 | Pinned config, deterministic training, reproducible candidate outputs |
| T-005 | Design Robust multi-asset collateral frontier with convex liquidity tail-risk charge. ablation only if needed | REQ-003 | Incremental complexity budget versus simple candidate recorded |
| T-006 | Freeze chronological holdout and matched economic replay | REQ-004,NFR-001,AC-003 | Same action set; no post-decision information; execution cost included |
| T-007 | Evaluate net economic revenue, risk capital per dollar, haircuts and eligibility breaches, retained lending volume.; stress Comparing unavailable cash reinvestment yield to executable noncash economics creates phantom spread. | REQ-004,AC-004 | CI/stress metrics and fail/abstention report generated |
| T-008 | Review legal/data boundaries, stop/go and shadow plan | NFR-002,AC-005 | Explicit independent reviewer sign-off; no automatic deployment |

## Acceptance-test mapping (planned)
- AC-001 → `test_cash_noncash_lending_collateral_frontier_asof`: sources unavailable at decision time must throw a typed error.
- AC-002 → `test_cash_noncash_lending_collateral_frontier_baseline`: compare with hand-calculated synthetic examples.
- AC-003 → `test_cash_noncash_lending_collateral_frontier_paired`: split embargo and matched action support.
- AC-004 → `test_cash_noncash_lending_collateral_frontier_risk`: bounds, stress and cost sensitivity.
- AC-005 → `test_cash_noncash_lending_collateral_frontier_public_gate`: confidential and unauthorized record rejection.

## Completion caveat
Only design documents exist. No test has been implemented or passed; DO NOT mark anything DONE until a verified run report and owner approval exists.
