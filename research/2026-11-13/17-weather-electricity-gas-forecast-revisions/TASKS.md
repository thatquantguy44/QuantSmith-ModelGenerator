# TASKS — Weather Forecast Revision as an Electricity-to-Gas Risk Hedge
**Status:** All tasks TODO. Proposed test names are NOT run or present in code.

| ID | Task | Requirements | Concrete definition of done |
|---|---|---|---|
| T-001 | Verify market/legal permissions and rights to NWS issued and archived forecasts, EIA balancing authority hourly load and generation, power/gas futures settlements and basis. | REQ-001,NFR-002 | Signed accessible-source and action/market eligibility matrix |
| T-002 | Build immutable `weather-electricity-gas-forecast-revisions` schema and synthetic fixtures at balancing authority × weather forecast issuance × lead hour | REQ-001,NFR-001,AC-001 | Future-vintage, duplicates and revisions rejected deterministically |
| T-003 | Implement Seasonal degree-day demand regression and absolute temperature forecasts. with realistic frictions | REQ-002,AC-002 | Math, units, feasibility and no-trade unit tests green |
| T-004 | Implement initial Net-load forecast-revision elasticity with non-linear stress threshold. | REQ-003,AC-003 | Pinned config, deterministic training, reproducible candidate outputs |
| T-005 | Design Probabilistic shortfall-and-constraint model with weather ensemble calibration. ablation only if needed | REQ-003 | Incremental complexity budget versus simple candidate recorded |
| T-006 | Freeze chronological holdout and matched economic replay | REQ-004,NFR-001,AC-003 | Same action set; no post-decision information; execution cost included |
| T-007 | Evaluate load p95 quantile loss, probabilistic calibration, hedge tracking error, net futures carry.; stress Archive of *historical forecasts as issued* may be inaccessible; today's historical observations are not contemporaneous forecasts. | REQ-004,AC-004 | CI/stress metrics and fail/abstention report generated |
| T-008 | Review legal/data boundaries, stop/go and shadow plan | NFR-002,AC-005 | Explicit independent reviewer sign-off; no automatic deployment |

## Acceptance-test mapping (planned)
- AC-001 → `test_weather_electricity_gas_forecast_revisions_asof`: sources unavailable at decision time must throw a typed error.
- AC-002 → `test_weather_electricity_gas_forecast_revisions_baseline`: compare with hand-calculated synthetic examples.
- AC-003 → `test_weather_electricity_gas_forecast_revisions_paired`: split embargo and matched action support.
- AC-004 → `test_weather_electricity_gas_forecast_revisions_risk`: bounds, stress and cost sensitivity.
- AC-005 → `test_weather_electricity_gas_forecast_revisions_public_gate`: confidential and unauthorized record rejection.

## Completion caveat
Only design documents exist. No test has been implemented or passed; DO NOT mark anything DONE until a verified run report and owner approval exists.
