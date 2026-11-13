# PLAN — AI Infrastructure Capex-to-Power-and-Export Supply Chain Factor
**Status:** Proposed architecture only · **Specification:** [SPEC.md](./SPEC.md)

## Architecture
`source catalogs → license + availability validator → ai-capex-power-export-factor time-vintaged panel → feasible benchmark → candidate → independent economic replay → evidence ledger → human gate`

### A. Source adapters and data lineage
SEC EDGAR filed capital expenditure and commitments, EIA power demand/generation, public utility service-area reports, UN Comtrade semiconductor/electrical equipment trade. **Observation grain:** public company disclosure × filing-time vintage × geography × monthly energy/trade release. **Decision horizon:** rebalance monthly after latest public filings, energy updates and international trade release.
**Public proxy adequacy:** SEC filing disclosures, EIA grid observations and UN Comtrade aggregate products; issuer-level mapping is research inference.
Private inputs, if later approved, remain segregated and unavailable to public GitHub, Slack or public LLM prompts.

### B. Core baseline and model
- **Baseline first:** Equal-weight US tech/utility/semiconductor thematic basket with broad market hedge.. Record every eligibility, cost and data-filter assumption.
- **Candidate:** Supply-chain bottleneck score anchored in publicly observed physical constraints..
- **Advanced:** Bayesian uncertainty propagation across disclosed commitments, supply chains and commodity/electricity capacity.. Only attempt if candidate clears a preregistered incremental-complexity hurdle.
- **Objective:** Bottleneck_t = min(grid_capacity_t/expected_load_t, export_supply_t/needed_components_t); signal_i,t=exposure_i*(Bottleneck_t-1)
- **Variable meaning:** expected_load and needed_components are explicit assumptions, not observable facts; no inferral of private company data-center locations.

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
Disclosure boilerplate, future guidance and partial energy-grid footprint can generate strong hindsight mapping bias.
Investigate whether a robust baseline or simpler model already achieves similar outcomes. Accept model abstention as a valid action when inputs are insufficient.

### F. Traceability and test matrix
REQ-001 → T-001,T-002; REQ-002 → T-003; REQ-003 → T-004,T-005; REQ-004 → T-006,T-007; NFR-001 → T-002,T-006; NFR-002 → T-001,T-008.
AC-001..AC-005 map to synthetic and holdout tests in [TASKS.md](./TASKS.md).

### G. Rollout
Public source feasibility → synthetic schema tests → licensed/approved actual data → costed backtest → shadow evaluation → human go/no-go; all downstream steps blocked until evidenced.
