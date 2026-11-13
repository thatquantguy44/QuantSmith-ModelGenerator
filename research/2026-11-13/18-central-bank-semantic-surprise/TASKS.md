# TASKS — Central-Bank Communication Semantic Surprise Across Languages
**Status:** All tasks TODO. Proposed test names are NOT run or present in code.

| ID | Task | Requirements | Concrete definition of done |
|---|---|---|---|
| T-001 | Verify market/legal permissions and rights to Versioned official policy statements; actual publication timestamps; pre-event interest rate futures; FX and rates price bars; translated text audit. | REQ-001,NFR-002 | Signed accessible-source and action/market eligibility matrix |
| T-002 | Build immutable `central-bank-semantic-surprise` schema and synthetic fixtures at central-bank event × original language × statement version × publication timestamp | REQ-001,NFR-001,AC-001 | Future-vintage, duplicates and revisions rejected deterministically |
| T-003 | Implement Policy rate surprise (or no-surprise dummy without licensed expectation) and prior-day rate changes. with realistic frictions | REQ-002,AC-002 | Math, units, feasibility and no-trade unit tests green |
| T-004 | Implement initial Source-grounded claim-difference extractor with multilingual uncertainty and simple linear evaluation. | REQ-003,AC-003 | Pinned config, deterministic training, reproducible candidate outputs |
| T-005 | Design Constrained multilingual textual event state-space with calibration and abstention threshold. ablation only if needed | REQ-003 | Incremental complexity budget versus simple candidate recorded |
| T-006 | Freeze chronological holdout and matched economic replay | REQ-004,NFR-001,AC-003 | Same action set; no post-decision information; execution cost included |
| T-007 | Evaluate out-of-sample price direction log loss, FX hedge information ratio, translation agreement and unsupported claim rate.; stress Translation distortions, backfilled statement updates, and post-event news leakage are especially severe for multilingual event models. | REQ-004,AC-004 | CI/stress metrics and fail/abstention report generated |
| T-008 | Review legal/data boundaries, stop/go and shadow plan | NFR-002,AC-005 | Explicit independent reviewer sign-off; no automatic deployment |

## Acceptance-test mapping (planned)
- AC-001 → `test_central_bank_semantic_surprise_asof`: sources unavailable at decision time must throw a typed error.
- AC-002 → `test_central_bank_semantic_surprise_baseline`: compare with hand-calculated synthetic examples.
- AC-003 → `test_central_bank_semantic_surprise_paired`: split embargo and matched action support.
- AC-004 → `test_central_bank_semantic_surprise_risk`: bounds, stress and cost sensitivity.
- AC-005 → `test_central_bank_semantic_surprise_public_gate`: confidential and unauthorized record rejection.

## Completion caveat
Only design documents exist. No test has been implemented or passed; DO NOT mark anything DONE until a verified run report and owner approval exists.
