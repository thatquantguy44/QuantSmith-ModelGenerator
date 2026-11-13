# TASKS — Trade-Network Export-Shock Transmission to Equity Sectors
**Status:** All tasks TODO. Proposed test names are NOT run or present in code.

| ID | Task | Requirements | Concrete definition of done |
|---|---|---|---|
| T-001 | Verify market/legal permissions and rights to UN Comtrade reported and partner-reported trade by HS code/month; sector country revenue mix; FX; sector returns and macro controls. | REQ-001,NFR-002 | Signed accessible-source and action/market eligibility matrix |
| T-002 | Build immutable `trade-network-export-shocks` schema and synthetic fixtures at reporter × partner × HS code × reference month × publication/availability timestamp | REQ-001,NFR-001,AC-001 | Future-vintage, duplicates and revisions rejected deterministically |
| T-003 | Implement Equal-weight country sector allocation with FX and local industrial production controls. with realistic frictions | REQ-002,AC-002 | Math, units, feasibility and no-trade unit tests green |
| T-004 | Implement initial Sparse directed trade graph factor with event-lag-aware regressions. | REQ-003,AC-003 | Pinned config, deterministic training, reproducible candidate outputs |
| T-005 | Design Causal graph neural propagation with hard release-vintage masking and sector earnings transmission. ablation only if needed | REQ-003 | Incremental complexity budget versus simple candidate recorded |
| T-006 | Freeze chronological holdout and matched economic replay | REQ-004,NFR-001,AC-003 | Same action set; no post-decision information; execution cost included |
| T-007 | Evaluate OOS sector information coefficient, dollar-neutral Sharpe, earnings revision hit rate, turnover and tail loss.; stress Revisions, late reporters, trade re-exports and mapping HS codes to listed firms can create survivorship and spurious exposure. | REQ-004,AC-004 | CI/stress metrics and fail/abstention report generated |
| T-008 | Review legal/data boundaries, stop/go and shadow plan | NFR-002,AC-005 | Explicit independent reviewer sign-off; no automatic deployment |

## Acceptance-test mapping (planned)
- AC-001 → `test_trade_network_export_shocks_asof`: sources unavailable at decision time must throw a typed error.
- AC-002 → `test_trade_network_export_shocks_baseline`: compare with hand-calculated synthetic examples.
- AC-003 → `test_trade_network_export_shocks_paired`: split embargo and matched action support.
- AC-004 → `test_trade_network_export_shocks_risk`: bounds, stress and cost sensitivity.
- AC-005 → `test_trade_network_export_shocks_public_gate`: confidential and unauthorized record rejection.

## Completion caveat
Only design documents exist. No test has been implemented or passed; DO NOT mark anything DONE until a verified run report and owner approval exists.
