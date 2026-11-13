# PLAN — CFTC Positioning Concentration and Commodity Curve Convexity
**Status:** Proposed architecture only · **Specification:** [SPEC.md](./SPEC.md)

## Architecture
`source catalogs → license + availability validator → cot-crowding-curve-convexity time-vintaged panel → feasible benchmark → candidate → independent economic replay → evidence ledger → human gate`

### A. Source adapters and data lineage
CFTC Disaggregated COT futures positions, futures contracts prices/rolls, EIA physical inventories where applicable. **Observation grain:** CFTC contract market × Tuesday reference position × Friday public release, then weekly trade clock. **Decision horizon:** earliest action is CFTC publication/next executable session; no use of Tuesday positions on Tuesday.
**Public proxy adequacy:** CFTC public positioning has Tuesday reference dates and Friday releases; curve prices may be delayed/paid.
Private inputs, if later approved, remain segregated and unavailable to public GitHub, Slack or public LLM prompts.

### B. Core baseline and model
- **Baseline first:** Futures curve carry/roll-yield and 12-month time-series momentum.. Record every eligibility, cost and data-filter assumption.
- **Candidate:** Positioning-conditioned conditional expected shortfall regression..
- **Advanced:** Stochastic inventory-demand equilibrium with nonlinear dealer hedging and curve impact.. Only attempt if candidate clears a preregistered incremental-complexity hurdle.
- **Objective:** Crowding_t=(spec_long_t-spec_short_t)/OI_t; Convexity_t=F1_t-2F2_t+F3_t; TailScore_t=β*Crowding_t*Convexity_t
- **Variable meaning:** F1..F3 are aligned futures maturities with explicit roll rules; OI is the reported futures open interest, all at publication availability.

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
CFTC taxonomy changes, combined report double-counting and slow publication may annihilate predictive edge.
Investigate whether a robust baseline or simpler model already achieves similar outcomes. Accept model abstention as a valid action when inputs are insufficient.

### F. Traceability and test matrix
REQ-001 → T-001,T-002; REQ-002 → T-003; REQ-003 → T-004,T-005; REQ-004 → T-006,T-007; NFR-001 → T-002,T-006; NFR-002 → T-001,T-008.
AC-001..AC-005 map to synthetic and holdout tests in [TASKS.md](./TASKS.md).

### G. Rollout
Public source feasibility → synthetic schema tests → licensed/approved actual data → costed backtest → shadow evaluation → human go/no-go; all downstream steps blocked until evidenced.
