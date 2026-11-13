# TASKS — EM External-Funding Fragility via Currency Mismatch and IIP
**Status:** All tasks TODO. Proposed test names are NOT run or present in code.

| ID | Task | Requirements | Concrete definition of done |
|---|---|---|---|
| T-001 | Verify market/legal permissions and rights to IMF IIP, BIS global liquidity quarterly FX credit, OECD macro where available, public reserve series and FX/sovereign returns. | REQ-001,NFR-002 | Signed accessible-source and action/market eligibility matrix |
| T-002 | Build immutable `em-external-funding-fragility` schema and synthetic fixtures at country × reporting quarter × first-public-availability time | REQ-001,NFR-001,AC-001 | Future-vintage, duplicates and revisions rejected deterministically |
| T-003 | Implement Traditional sovereign credit rating tier, FX carry and three-month realized volatility. with realistic frictions | REQ-002,AC-002 | Math, units, feasibility and no-trade unit tests green |
| T-004 | Implement initial Point-in-time standardized funding mismatch factor with recession/regime interactions. | REQ-003,AC-003 | Pinned config, deterministic training, reproducible candidate outputs |
| T-005 | Design Joint skewed macro-financial state-space with robust optimization and missing vintage uncertainty. ablation only if needed | REQ-003 | Incremental complexity budget versus simple candidate recorded |
| T-006 | Freeze chronological holdout and matched economic replay | REQ-004,NFR-001,AC-003 | Same action set; no post-decision information; execution cost included |
| T-007 | Evaluate EM FX crash recall, max drawdown, FX-adjusted stress Brier, portfolio VaR breaches.; stress Global liquidity metrics are quarterly; imputed weekly updates are model estimates, not observations. | REQ-004,AC-004 | CI/stress metrics and fail/abstention report generated |
| T-008 | Review legal/data boundaries, stop/go and shadow plan | NFR-002,AC-005 | Explicit independent reviewer sign-off; no automatic deployment |

## Acceptance-test mapping (planned)
- AC-001 → `test_em_external_funding_fragility_asof`: sources unavailable at decision time must throw a typed error.
- AC-002 → `test_em_external_funding_fragility_baseline`: compare with hand-calculated synthetic examples.
- AC-003 → `test_em_external_funding_fragility_paired`: split embargo and matched action support.
- AC-004 → `test_em_external_funding_fragility_risk`: bounds, stress and cost sensitivity.
- AC-005 → `test_em_external_funding_fragility_public_gate`: confidential and unauthorized record rejection.

## Completion caveat
Only design documents exist. No test has been implemented or passed; DO NOT mark anything DONE until a verified run report and owner approval exists.
