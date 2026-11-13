# PLAN — Settlement-Fail Buy-In versus Wait Optimal Stopping
**Status:** Proposed architecture only · **Specification:** [SPEC.md](./SPEC.md)

## Architecture
`source catalogs → license + availability validator → fail-buyin-optimal-stopping time-vintaged panel → feasible benchmark → candidate → independent economic replay → evidence ledger → human gate`

### A. Source adapters and data lineage
Public dealer failure aggregates for calibration; synthetic failure life histories; approved buy-in quotes, fails charges and legal remedies. **Observation grain:** failed settlement instruction × elapsed failed day × cut-off timestamp. **Decision horizon:** business-day cure decisions only after confirmed fail and remedy eligibility.
**Public proxy adequacy:** Primary dealer fails are aggregate benchmarks, not individual securities or cost histories.
Private inputs, if later approved, remain segregated and unavailable to public GitHub, Slack or public LLM prompts.

### B. Core baseline and model
- **Baseline first:** Auto-escalate after fixed N-day failure age.. Record every eligibility, cost and data-filter assumption.
- **Candidate:** Discrete-time survival model with exact dynamic-programming stopping rule..
- **Advanced:** Partial-observation optimal stopping with supply scarcity and stochastic cover price.. Only attempt if candidate clears a preregistered incremental-complexity hurdle.
- **Objective:** V_t(s)=min{cover_cost_t(s), reroute_cost_t(s), fail_penalty_t(s)+E[V_(t+1)(s')|s]}
- **Variable meaning:** s contains security, counterparty, days failed, available cover liquidity and contractual remedy state.

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
Fails charges and rights to enforce buy-ins differ by asset, market and contract; wrong assumptions invalidate decisions.
Investigate whether a robust baseline or simpler model already achieves similar outcomes. Accept model abstention as a valid action when inputs are insufficient.

### F. Traceability and test matrix
REQ-001 → T-001,T-002; REQ-002 → T-003; REQ-003 → T-004,T-005; REQ-004 → T-006,T-007; NFR-001 → T-002,T-006; NFR-002 → T-001,T-008.
AC-001..AC-005 map to synthetic and holdout tests in [TASKS.md](./TASKS.md).

### G. Rollout
Public source feasibility → synthetic schema tests → licensed/approved actual data → costed backtest → shadow evaluation → human go/no-go; all downstream steps blocked until evidenced.
