# PLAN — Dynamic Currency-Hedge and Rebalancing Tax for Global Equity
**Status:** Proposed architecture only · **Specification:** [SPEC.md](./SPEC.md)

## Architecture
`source catalogs → license + availability validator → global-equity-dynamic-fx-hedge time-vintaged panel → feasible benchmark → candidate → independent economic replay → evidence ledger → human gate`

### A. Source adapters and data lineage
Country index total returns, currency spot/forward curves, FX liquidity, investability restrictions and funding rates. **Observation grain:** country equity market × FX forward tenor × monthly rebalance date. **Decision horizon:** rebalance at scheduled month-end using prior-close prices and then-available forward quotes.
**Public proxy adequacy:** MSCI publishes methodology, not unrestricted total return/constituent history; FX and rates data may have licensing restrictions.
Private inputs, if later approved, remain segregated and unavailable to public GitHub, Slack or public LLM prompts.

### B. Core baseline and model
- **Baseline first:** 50% static currency hedges plus equal-risk country weights and quarterly turnover.. Record every eligibility, cost and data-filter assumption.
- **Candidate:** Robust covariance and transaction-cost-aware FX hedge optimizer..
- **Advanced:** Distributionally robust conditional hedge allocation with Markov stress regime and partial hedging.. Only attempt if candidate clears a preregistered incremental-complexity hurdle.
- **Objective:** min_(w,h) E[(R_equity(w)+R_FX(w,h)-target)^2] + λ*ES_95 + μ*turnover(w,h); 0≤h_c≤hmax_c
- **Variable meaning:** w are country equity weights; h_c hedge fractions; ES_95 is expected shortfall; forward carry and bid/ask are charged at actual roll.

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
Country index histories have vendor survivorship and free-float methodological changes; FX pricing may be unavailable at allocated size.
Investigate whether a robust baseline or simpler model already achieves similar outcomes. Accept model abstention as a valid action when inputs are insufficient.

### F. Traceability and test matrix
REQ-001 → T-001,T-002; REQ-002 → T-003; REQ-003 → T-004,T-005; REQ-004 → T-006,T-007; NFR-001 → T-002,T-006; NFR-002 → T-001,T-008.
AC-001..AC-005 map to synthetic and holdout tests in [TASKS.md](./TASKS.md).

### G. Rollout
Public source feasibility → synthetic schema tests → licensed/approved actual data → costed backtest → shadow evaluation → human go/no-go; all downstream steps blocked until evidenced.
