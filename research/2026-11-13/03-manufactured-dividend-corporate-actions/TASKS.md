# TASKS — Manufactured-Dividend and Corporate-Action Loan Economics
**Status:** All tasks TODO. Proposed test names are NOT run or present in code.

| ID | Task | Requirements | Concrete definition of done |
|---|---|---|---|
| T-001 | Verify market/legal permissions and rights to Ex/record/pay dates; loan life; fee accrual; event elections; dividend amounts; owner tax flags and permitted return/recall rules. | REQ-001,NFR-002 | Signed accessible-source and action/market eligibility matrix |
| T-002 | Build immutable `manufactured-dividend-corporate-actions` schema and synthetic fixtures at security × beneficial owner program × corporate-action event × decision timestamp | REQ-001,NFR-001,AC-001 | Future-vintage, duplicates and revisions rejected deterministically |
| T-003 | Implement Renew if lending fee remains positive and return only upon explicit mandatory recall. with realistic frictions | REQ-002,AC-002 | Math, units, feasibility and no-trade unit tests green |
| T-004 | Implement initial Rule-checked event economics and constrained loan life-cycle integer optimizer. | REQ-003,AC-003 | Pinned config, deterministic training, reproducible candidate outputs |
| T-005 | Design Scenario tree for unresolved election announcements and corporate action adjustment ranges. ablation only if needed | REQ-003 | Incremental complexity budget versus simple candidate recorded |
| T-006 | Freeze chronological holdout and matched economic replay | REQ-004,NFR-001,AC-003 | Same action set; no post-decision information; execution cost included |
| T-007 | Evaluate net program income, missed payment events, operational exceptions, unauthorized action count.; stress Tax withholding, treaty benefits and manufactured-dividend treatment cannot be assumed from issuer-country information alone. | REQ-004,AC-004 | CI/stress metrics and fail/abstention report generated |
| T-008 | Review legal/data boundaries, stop/go and shadow plan | NFR-002,AC-005 | Explicit independent reviewer sign-off; no automatic deployment |

## Acceptance-test mapping (planned)
- AC-001 → `test_manufactured_dividend_corporate_actions_asof`: sources unavailable at decision time must throw a typed error.
- AC-002 → `test_manufactured_dividend_corporate_actions_baseline`: compare with hand-calculated synthetic examples.
- AC-003 → `test_manufactured_dividend_corporate_actions_paired`: split embargo and matched action support.
- AC-004 → `test_manufactured_dividend_corporate_actions_risk`: bounds, stress and cost sensitivity.
- AC-005 → `test_manufactured_dividend_corporate_actions_public_gate`: confidential and unauthorized record rejection.

## Completion caveat
Only design documents exist. No test has been implemented or passed; DO NOT mark anything DONE until a verified run report and owner approval exists.
