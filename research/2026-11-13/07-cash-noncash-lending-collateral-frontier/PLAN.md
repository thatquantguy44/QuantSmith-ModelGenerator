# PLAN — Cash versus Noncash Loan-Collateral Economic Frontier
**Status:** Proposed architecture only · **Specification:** [SPEC.md](./SPEC.md)

## Architecture
`source catalogs → license + availability validator → cash-noncash-lending-collateral-frontier time-vintaged panel → feasible benchmark → candidate → independent economic replay → evidence ledger → human gate`

### A. Source adapters and data lineage
Cash and noncash terms, rebate schedules, reinvestment constraints, asset eligibility, mark-to-market, haircuts and legal restrictions. **Observation grain:** loan offer × collateral type × owner mandate × quotation timestamp. **Decision horizon:** quote acceptance before loan opening with known collateral terms, not end-of-day realized earnings.
**Public proxy adequacy:** Official repo market rates provide funding context; collateral-type price schedules are program-specific.
Private inputs, if later approved, remain segregated and unavailable to public GitHub, Slack or public LLM prompts.

### B. Core baseline and model
- **Baseline first:** Choose the highest headline loan spread among eligible offers.. Record every eligibility, cost and data-filter assumption.
- **Candidate:** Loan-specific all-in economic break-even and constraints solver..
- **Advanced:** Robust multi-asset collateral frontier with convex liquidity tail-risk charge.. Only attempt if candidate clears a preregistered incremental-complexity hurdle.
- **Objective:** max_(j∈allowed) [borrow_fee_j + permissible_reinvestment_yield_j - rebate_j - liquidity_cost_j - expected_loss_j - capital_j]
- **Variable meaning:** j denotes a feasible collateral convention; values must use common horizon and comparable currency-adjusted cash flows.

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
Comparing unavailable cash reinvestment yield to executable noncash economics creates phantom spread.
Investigate whether a robust baseline or simpler model already achieves similar outcomes. Accept model abstention as a valid action when inputs are insufficient.

### F. Traceability and test matrix
REQ-001 → T-001,T-002; REQ-002 → T-003; REQ-003 → T-004,T-005; REQ-004 → T-006,T-007; NFR-001 → T-002,T-006; NFR-002 → T-001,T-008.
AC-001..AC-005 map to synthetic and holdout tests in [TASKS.md](./TASKS.md).

### G. Rollout
Public source feasibility → synthetic schema tests → licensed/approved actual data → costed backtest → shadow evaluation → human go/no-go; all downstream steps blocked until evidenced.
