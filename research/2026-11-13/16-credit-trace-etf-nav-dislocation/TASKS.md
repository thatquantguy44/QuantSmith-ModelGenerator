# TASKS — Corporate-Bond TRACE Liquidity-to-ETF NAV Stress Transmission
**Status:** All tasks TODO. Proposed test names are NOT run or present in code.

| ID | Task | Requirements | Concrete definition of done |
|---|---|---|---|
| T-001 | Verify market/legal permissions and rights to FINRA TRACE public aggregate/trade pages, subscription historical bond records, ETF market prices, NAV timestamps, bond indices, CDX basis. | REQ-001,NFR-002 | Signed accessible-source and action/market eligibility matrix |
| T-002 | Build immutable `credit-trace-etf-nav-dislocation` schema and synthetic fixtures at bond × disseminated trade timestamp × ETF NAV publication timestamp | REQ-001,NFR-001,AC-001 | Future-vintage, duplicates and revisions rejected deterministically |
| T-003 | Implement ETF realized volatility and quoted bid-ask spread. with realistic frictions | REQ-002,AC-002 | Math, units, feasibility and no-trade unit tests green |
| T-004 | Implement initial Robust bond-liquidity dispersion index and ETF tracking-state model. | REQ-003,AC-003 | Pinned config, deterministic training, reproducible candidate outputs |
| T-005 | Design Structural ETF redemption/creation network with dealer intermediation bottlenecks. ablation only if needed | REQ-003 | Incremental complexity budget versus simple candidate recorded |
| T-006 | Freeze chronological holdout and matched economic replay | REQ-004,NFR-001,AC-003 | Same action set; no post-decision information; execution cost included |
| T-007 | Evaluate tracking error forecast, credit tail loss, hedge slippage, redemption-state calibration.; stress Reported bond prices may be size-capped/delayed; TRACE trade access/licensing varies and NAV can embed stale marks. | REQ-004,AC-004 | CI/stress metrics and fail/abstention report generated |
| T-008 | Review legal/data boundaries, stop/go and shadow plan | NFR-002,AC-005 | Explicit independent reviewer sign-off; no automatic deployment |

## Acceptance-test mapping (planned)
- AC-001 → `test_credit_trace_etf_nav_dislocation_asof`: sources unavailable at decision time must throw a typed error.
- AC-002 → `test_credit_trace_etf_nav_dislocation_baseline`: compare with hand-calculated synthetic examples.
- AC-003 → `test_credit_trace_etf_nav_dislocation_paired`: split embargo and matched action support.
- AC-004 → `test_credit_trace_etf_nav_dislocation_risk`: bounds, stress and cost sensitivity.
- AC-005 → `test_credit_trace_etf_nav_dislocation_public_gate`: confidential and unauthorized record rejection.

## Completion caveat
Only design documents exist. No test has been implemented or passed; DO NOT mark anything DONE until a verified run report and owner approval exists.
