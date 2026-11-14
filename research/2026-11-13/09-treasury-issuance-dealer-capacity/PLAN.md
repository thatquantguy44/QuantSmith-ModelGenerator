# PLAN — Treasury Issuance-to-Dealer Intermediation Capacity Map
**Status:** Proposed architecture only · **Specification:** [SPEC.md](./SPEC.md)

## Architecture
`source catalogs → license + availability validator → treasury-issuance-dealer-capacity time-vintaged panel → feasible benchmark → candidate → independent economic replay → evidence ledger → human gate`

### A. Source adapters and data lineage
Treasury auction issuance and settlement schedule; weekly primary dealer net positions/financing; OFR repo aggregates; public Treasury yield changes. **Observation grain:** issuance cohort × week of publicly released dealer aggregates. **Decision horizon:** weekly close after primary dealer publication; never treat reported prior-week positions as contemporaneous.
**Public proxy adequacy:** Treasury and NY Fed release events and dealer statistics publicly, though publication lags must be retained.
Private inputs, if later approved, remain segregated and unavailable to public GitHub, Slack or public LLM prompts.

### B. Core baseline and model
- **Baseline first:** Treasury yield volatility and calendar week indicators.. Record every eligibility, cost and data-filter assumption.
- **Candidate:** Event-study + state-space dealer supply absorption proxy..
- **Advanced:** Instrumented quasi-experiment using prescheduled auction supply shocks and cross-CUSIP constraints.. Only attempt if candidate clears a preregistered incremental-complexity hurdle.
- **Objective:** C_t=Δissuance_t - β*Δdealer_financed_positions_t; p_(t+h)=sigmoid(α+γ*C_(available≤t)+δ*vol_t)
- **Variable meaning:** C_t is an issuance-absorption mismatch proxy, not observed dealer capital; p is stress probability, h is pre-set future horizon.

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
Aggregate dealer reports cannot identify securities or dealers and issuance is endogenous to financing conditions.
Investigate whether a robust baseline or simpler model already achieves similar outcomes. Accept model abstention as a valid action when inputs are insufficient.

### F. Traceability and test matrix
REQ-001 → T-001,T-002; REQ-002 → T-003; REQ-003 → T-004,T-005; REQ-004 → T-006,T-007; NFR-001 → T-002,T-006; NFR-002 → T-001,T-008.
AC-001..AC-005 map to synthetic and holdout tests in [TASKS.md](./TASKS.md).

### G. Rollout
Public source feasibility → synthetic schema tests → licensed/approved actual data → costed backtest → shadow evaluation → human go/no-go; all downstream steps blocked until evidenced.
