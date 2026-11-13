# PLAN — US–Euro Sovereign Curve Shock Decomposition with Data Vintages
**Status:** Proposed architecture only · **Specification:** [SPEC.md](./SPEC.md)

## Architecture
`source catalogs → license + availability validator → us-euro-curve-release-shocks time-vintaged panel → feasible benchmark → candidate → independent economic replay → evidence ledger → human gate`

### A. Source adapters and data lineage
ECB published euro yield curve, US yields and ALFRED macro vintages, official release times, FX hedges, rates futures cost. **Observation grain:** economic release event × curve tenor × publication instant × geography. **Decision horizon:** end-of-release or next-session decision after releases disseminate; avoid falsely assuming instant access to revised series.
**Public proxy adequacy:** ECB and FRED provide curves/vintages but not executable futures bid/ask or consensus expectation snapshots.
Private inputs, if later approved, remain segregated and unavailable to public GitHub, Slack or public LLM prompts.

### B. Core baseline and model
- **Baseline first:** 60-day rolling DV01-neutral cross-market beta hedge.. Record every eligibility, cost and data-filter assumption.
- **Candidate:** Vintaged announcement factor model plus shrinkage hedge weights..
- **Advanced:** Hierarchical structural yield-curve state-space with distinct real-rate and term-premium factor loading.. Only attempt if candidate clears a preregistered incremental-complexity hurdle.
- **Objective:** Δy_US,t = β1*Surprise_US,t + β2*Surprise_EU,t + u_t; h*=argmin_h E[(ΔP_US+h*ΔP_EU)^2]+turnover_cost(h)
- **Variable meaning:** y is sovereign yield; Surprise is actual release minus consensus known beforehand (consensus may require licensing); h is DV01-scaled hedge.

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
Public releases cannot recreate market consensus surprises without a licensed historical consensus dataset or explicit no-consensus baseline.
Investigate whether a robust baseline or simpler model already achieves similar outcomes. Accept model abstention as a valid action when inputs are insufficient.

### F. Traceability and test matrix
REQ-001 → T-001,T-002; REQ-002 → T-003; REQ-003 → T-004,T-005; REQ-004 → T-006,T-007; NFR-001 → T-002,T-006; NFR-002 → T-001,T-008.
AC-001..AC-005 map to synthetic and holdout tests in [TASKS.md](./TASKS.md).

### G. Rollout
Public source feasibility → synthetic schema tests → licensed/approved actual data → costed backtest → shadow evaluation → human go/no-go; all downstream steps blocked until evidenced.
