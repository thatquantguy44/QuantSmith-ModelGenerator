# TASKS — Treasury Issuance-to-Dealer Intermediation Capacity Map
**Status:** All tasks TODO. Proposed test names are NOT run or present in code.

| ID | Task | Requirements | Concrete definition of done |
|---|---|---|---|
| T-001 | Verify market/legal permissions and rights to Treasury auction issuance and settlement schedule; weekly primary dealer net positions/financing; OFR repo aggregates; public Treasury yield changes. | REQ-001,NFR-002 | Signed accessible-source and action/market eligibility matrix |
| T-002 | Build immutable `treasury-issuance-dealer-capacity` schema and synthetic fixtures at issuance cohort × week of publicly released dealer aggregates | REQ-001,NFR-001,AC-001 | Future-vintage, duplicates and revisions rejected deterministically |
| T-003 | Implement Treasury yield volatility and calendar week indicators. with realistic frictions | REQ-002,AC-002 | Math, units, feasibility and no-trade unit tests green |
| T-004 | Implement initial Event-study + state-space dealer supply absorption proxy. | REQ-003,AC-003 | Pinned config, deterministic training, reproducible candidate outputs |
| T-005 | Design Instrumented quasi-experiment using prescheduled auction supply shocks and cross-CUSIP constraints. ablation only if needed | REQ-003 | Incremental complexity budget versus simple candidate recorded |
| T-006 | Freeze chronological holdout and matched economic replay | REQ-004,NFR-001,AC-003 | Same action set; no post-decision information; execution cost included |
| T-007 | Evaluate stress forecast Brier, AUPRC, lead-time, false positives and hedge drawdown.; stress Aggregate dealer reports cannot identify securities or dealers and issuance is endogenous to financing conditions. | REQ-004,AC-004 | CI/stress metrics and fail/abstention report generated |
| T-008 | Review legal/data boundaries, stop/go and shadow plan | NFR-002,AC-005 | Explicit independent reviewer sign-off; no automatic deployment |

## Acceptance-test mapping (planned)
- AC-001 → `test_treasury_issuance_dealer_capacity_asof`: sources unavailable at decision time must throw a typed error.
- AC-002 → `test_treasury_issuance_dealer_capacity_baseline`: compare with hand-calculated synthetic examples.
- AC-003 → `test_treasury_issuance_dealer_capacity_paired`: split embargo and matched action support.
- AC-004 → `test_treasury_issuance_dealer_capacity_risk`: bounds, stress and cost sensitivity.
- AC-005 → `test_treasury_issuance_dealer_capacity_public_gate`: confidential and unauthorized record rejection.

## Completion caveat
Only design documents exist. No test has been implemented or passed; DO NOT mark anything DONE until a verified run report and owner approval exists.
