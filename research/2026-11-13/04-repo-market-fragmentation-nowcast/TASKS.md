# TASKS — Cleared Versus Tri-Party Repo Fragmentation Nowcast
**Status:** All tasks TODO. Proposed test names are NOT run or present in code.

| ID | Task | Requirements | Concrete definition of done |
|---|---|---|---|
| T-001 | Verify market/legal permissions and rights to OFR cleared and tri-party rate-volume series; collateral categories; SOFR; weekly dealer aggregate financing; release metadata. | REQ-001,NFR-002 | Signed accessible-source and action/market eligibility matrix |
| T-002 | Build immutable `repo-market-fragmentation-nowcast` schema and synthetic fixtures at venue × collateral class × tenor × underlying observation date, plus public publication timestamp | REQ-001,NFR-001,AC-001 | Future-vintage, duplicates and revisions rejected deterministically |
| T-003 | Implement SOFR level change and aggregate funding volume z-score. with realistic frictions | REQ-002,AC-002 | Math, units, feasibility and no-trade unit tests green |
| T-004 | Implement initial State-space latent fragmentation index with lag-aware missingness. | REQ-003,AC-003 | Pinned config, deterministic training, reproducible candidate outputs |
| T-005 | Design Hierarchical online change-point and causal regime attribution by venue and reporting channel. ablation only if needed | REQ-003 | Incremental complexity budget versus simple candidate recorded |
| T-006 | Freeze chronological holdout and matched economic replay | REQ-004,NFR-001,AC-003 | Same action set; no post-decision information; execution cost included |
| T-007 | Evaluate next-session stress AUPRC, calibrated Brier score, false alarm rate, funding stress drawdown.; stress Revised/missing suppressed OFR cells and cross-venue holiday timing can create lookahead and artificial divergences. | REQ-004,AC-004 | CI/stress metrics and fail/abstention report generated |
| T-008 | Review legal/data boundaries, stop/go and shadow plan | NFR-002,AC-005 | Explicit independent reviewer sign-off; no automatic deployment |

## Acceptance-test mapping (planned)
- AC-001 → `test_repo_market_fragmentation_nowcast_asof`: sources unavailable at decision time must throw a typed error.
- AC-002 → `test_repo_market_fragmentation_nowcast_baseline`: compare with hand-calculated synthetic examples.
- AC-003 → `test_repo_market_fragmentation_nowcast_paired`: split embargo and matched action support.
- AC-004 → `test_repo_market_fragmentation_nowcast_risk`: bounds, stress and cost sensitivity.
- AC-005 → `test_repo_market_fragmentation_nowcast_public_gate`: confidential and unauthorized record rejection.

## Completion caveat
Only design documents exist. No test has been implemented or passed; DO NOT mark anything DONE until a verified run report and owner approval exists.
