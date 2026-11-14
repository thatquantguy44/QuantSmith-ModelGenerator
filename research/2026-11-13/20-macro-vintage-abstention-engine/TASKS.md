# TASKS — Macro-Vintage Integrity Engine with Prediction Abstention
**Status:** All tasks TODO. Proposed test names are NOT run or present in code.

| ID | Task | Requirements | Concrete definition of done |
|---|---|---|---|
| T-001 | Verify market/legal permissions and rights to ALFRED historical revisions, ECB yield releases, OECD SDMX data vintage calendars, US/global market proxies. | REQ-001,NFR-002 | Signed accessible-source and action/market eligibility matrix |
| T-002 | Build immutable `macro-vintage-abstention-engine` schema and synthetic fixtures at economic indicator × observation period × release date × vintage ID | REQ-001,NFR-001,AC-001 | Future-vintage, duplicates and revisions rejected deterministically |
| T-003 | Implement Always-on macro momentum score built from latest-vintage series. with realistic frictions | REQ-002,AC-002 | Math, units, feasibility and no-trade unit tests green |
| T-004 | Implement initial As-of macro feature store with release-confidence model and abstention. | REQ-003,AC-003 | Pinned config, deterministic training, reproducible candidate outputs |
| T-005 | Design Bayesian missing-data multiple-vintage filtering and conformal selective prediction with capacity-aware portfolio overlay. ablation only if needed | REQ-003 | Incremental complexity budget versus simple candidate recorded |
| T-006 | Freeze chronological holdout and matched economic replay | REQ-004,NFR-001,AC-003 | Same action set; no post-decision information; execution cost included |
| T-007 | Evaluate revision-induced backtest bias, selective risk loss, coverage, false alarm rate, time-to-data-availability.; stress ALFRED historical series coverage, future revisions and OECD methodological breaks can be incomplete; abstention selection bias. | REQ-004,AC-004 | CI/stress metrics and fail/abstention report generated |
| T-008 | Review legal/data boundaries, stop/go and shadow plan | NFR-002,AC-005 | Explicit independent reviewer sign-off; no automatic deployment |

## Acceptance-test mapping (planned)
- AC-001 → `test_macro_vintage_abstention_engine_asof`: sources unavailable at decision time must throw a typed error.
- AC-002 → `test_macro_vintage_abstention_engine_baseline`: compare with hand-calculated synthetic examples.
- AC-003 → `test_macro_vintage_abstention_engine_paired`: split embargo and matched action support.
- AC-004 → `test_macro_vintage_abstention_engine_risk`: bounds, stress and cost sensitivity.
- AC-005 → `test_macro_vintage_abstention_engine_public_gate`: confidential and unauthorized record rejection.

## Completion caveat
Only design documents exist. No test has been implemented or passed; DO NOT mark anything DONE until a verified run report and owner approval exists.
