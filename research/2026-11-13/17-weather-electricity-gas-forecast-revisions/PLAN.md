# PLAN — Weather Forecast Revision as an Electricity-to-Gas Risk Hedge
**Status:** Proposed architecture only · **Specification:** [SPEC.md](./SPEC.md)

## Architecture
`source catalogs → license + availability validator → weather-electricity-gas-forecast-revisions time-vintaged panel → feasible benchmark → candidate → independent economic replay → evidence ledger → human gate`

### A. Source adapters and data lineage
NWS issued and archived forecasts, EIA balancing authority hourly load and generation, power/gas futures settlements and basis. **Observation grain:** balancing authority × weather forecast issuance × lead hour. **Decision horizon:** forecast issuance is the earliest legal decision; never consume later realized weather or EIA actual load before release.
**Public proxy adequacy:** NWS API provides forecasts; EIA provides actual hourly grid operation data; forecast version history must be separately collected going forward.
Private inputs, if later approved, remain segregated and unavailable to public GitHub, Slack or public LLM prompts.

### B. Core baseline and model
- **Baseline first:** Seasonal degree-day demand regression and absolute temperature forecasts.. Record every eligibility, cost and data-filter assumption.
- **Candidate:** Net-load forecast-revision elasticity with non-linear stress threshold..
- **Advanced:** Probabilistic shortfall-and-constraint model with weather ensemble calibration.. Only attempt if candidate clears a preregistered incremental-complexity hurdle.
- **Objective:** Revision_r,t = LoadForecast_r,t^(latest issued) - LoadForecast_r,t^(prior issued); Hedge_t=clip(β*Revision_r,t,limits)
- **Variable meaning:** r is power balancing authority; revisions use two immutable issue-time snapshots; hedge maps only to liquid related assets with modeled cross-basis.

### C. Research interface contracts (not implemented)
`load_sources(as_of,license_context)` → versioned events;
`normalize(events,calendar)` → schema-validated, point-in-time features;
`feasible_actions(state)` → admissible decision set;
`run_baseline(states)` → benchmark actions;
`run_candidate(states,params)` → candidate actions;
`economic_replay(actions,execution)` → P&L/cost/risk;
`write_run_envelope()` → lineage, metrics, limitations.

### D. Constitution and reversibility
Correct-by-construction: no future release or illegal action in feasibility map.
Reversibility: shadow mode only and baseline-only kill switch.
Observability: log source vintage, dropped rows, solver status, rejected actions, inference confidence.
Security: only synthetic/official public information in artifacts.

### E. Alternative and failure analysis
Archive of *historical forecasts as issued* may be inaccessible; today's historical observations are not contemporaneous forecasts.
Investigate whether a robust baseline or simpler model already achieves similar outcomes. Accept model abstention as a valid action when inputs are insufficient.

### F. Traceability and test matrix
REQ-001 → T-001,T-002; REQ-002 → T-003; REQ-003 → T-004,T-005; REQ-004 → T-006,T-007; NFR-001 → T-002,T-006; NFR-002 → T-001,T-008.
AC-001..AC-005 map to synthetic and holdout tests in [TASKS.md](./TASKS.md).

### G. Rollout
Public source feasibility → synthetic schema tests → licensed/approved actual data → costed backtest → shadow evaluation → human go/no-go; all downstream steps blocked until evidenced.
