# TASKS — Securities-Lending Fee Observability & Selection-Bias Corrector
**Status:** All tasks TODO. Proposed test names are NOT run or present in code.

| ID | Task | Requirements | Concrete definition of done |
|---|---|---|---|
| T-001 | Verify market/legal permissions and rights to Contributed executed fee samples; public security volume/short-interest proxies; locate response metadata; source coverage and revisions. | REQ-001,NFR-002 | Signed accessible-source and action/market eligibility matrix |
| T-002 | Build immutable `lending-fee-selection-debiasing` schema and synthetic fixtures at security × lending day × vendor/contributor population | REQ-001,NFR-001,AC-001 | Future-vintage, duplicates and revisions rejected deterministically |
| T-003 | Implement Daily equally weighted or outstanding-value-weighted observed market fees. with realistic frictions | REQ-002,AC-002 | Math, units, feasibility and no-trade unit tests green |
| T-004 | Implement initial Doubly robust weighting with overlap and selection-sensitivity intervals. | REQ-003,AC-003 | Pinned config, deterministic training, reproducible candidate outputs |
| T-005 | Design Bayesian selection model with unverifiable missing-not-at-random stress bounds. ablation only if needed | REQ-003 | Incremental complexity budget versus simple candidate recorded |
| T-006 | Freeze chronological holdout and matched economic replay | REQ-004,NFR-001,AC-003 | Same action set; no post-decision information; execution cost included |
| T-007 | Evaluate cross-contributor benchmark error, interval coverage, abstention, quote drift, market breadth coverage.; stress Missing-not-at-random selection cannot be identified from executed loans alone; confidence intervals can be falsely narrow. | REQ-004,AC-004 | CI/stress metrics and fail/abstention report generated |
| T-008 | Review legal/data boundaries, stop/go and shadow plan | NFR-002,AC-005 | Explicit independent reviewer sign-off; no automatic deployment |

## Acceptance-test mapping (planned)
- AC-001 → `test_lending_fee_selection_debiasing_asof`: sources unavailable at decision time must throw a typed error.
- AC-002 → `test_lending_fee_selection_debiasing_baseline`: compare with hand-calculated synthetic examples.
- AC-003 → `test_lending_fee_selection_debiasing_paired`: split embargo and matched action support.
- AC-004 → `test_lending_fee_selection_debiasing_risk`: bounds, stress and cost sensitivity.
- AC-005 → `test_lending_fee_selection_debiasing_public_gate`: confidential and unauthorized record rejection.

## Completion caveat
Only design documents exist. No test has been implemented or passed; DO NOT mark anything DONE until a verified run report and owner approval exists.
