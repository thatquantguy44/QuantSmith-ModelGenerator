# TASKS — AI Infrastructure Capex-to-Power-and-Export Supply Chain Factor
**Status:** All tasks TODO. Proposed test names are NOT run or present in code.

| ID | Task | Requirements | Concrete definition of done |
|---|---|---|---|
| T-001 | Verify market/legal permissions and rights to SEC EDGAR filed capital expenditure and commitments, EIA power demand/generation, public utility service-area reports, UN Comtrade semiconductor/electrical equipment trade. | REQ-001,NFR-002 | Signed accessible-source and action/market eligibility matrix |
| T-002 | Build immutable `ai-capex-power-export-factor` schema and synthetic fixtures at public company disclosure × filing-time vintage × geography × monthly energy/trade release | REQ-001,NFR-001,AC-001 | Future-vintage, duplicates and revisions rejected deterministically |
| T-003 | Implement Equal-weight US tech/utility/semiconductor thematic basket with broad market hedge. with realistic frictions | REQ-002,AC-002 | Math, units, feasibility and no-trade unit tests green |
| T-004 | Implement initial Supply-chain bottleneck score anchored in publicly observed physical constraints. | REQ-003,AC-003 | Pinned config, deterministic training, reproducible candidate outputs |
| T-005 | Design Bayesian uncertainty propagation across disclosed commitments, supply chains and commodity/electricity capacity. ablation only if needed | REQ-003 | Incremental complexity budget versus simple candidate recorded |
| T-006 | Freeze chronological holdout and matched economic replay | REQ-004,NFR-001,AC-003 | Same action set; no post-decision information; execution cost included |
| T-007 | Evaluate sector-neutral residual return, realized earnings revision, stock/industry turnover and capacity sensitivity.; stress Disclosure boilerplate, future guidance and partial energy-grid footprint can generate strong hindsight mapping bias. | REQ-004,AC-004 | CI/stress metrics and fail/abstention report generated |
| T-008 | Review legal/data boundaries, stop/go and shadow plan | NFR-002,AC-005 | Explicit independent reviewer sign-off; no automatic deployment |

## Acceptance-test mapping (planned)
- AC-001 → `test_ai_capex_power_export_factor_asof`: sources unavailable at decision time must throw a typed error.
- AC-002 → `test_ai_capex_power_export_factor_baseline`: compare with hand-calculated synthetic examples.
- AC-003 → `test_ai_capex_power_export_factor_paired`: split embargo and matched action support.
- AC-004 → `test_ai_capex_power_export_factor_risk`: bounds, stress and cost sensitivity.
- AC-005 → `test_ai_capex_power_export_factor_public_gate`: confidential and unauthorized record rejection.

## Completion caveat
Only design documents exist. No test has been implemented or passed; DO NOT mark anything DONE until a verified run report and owner approval exists.
