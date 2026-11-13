# PLAN — Corporate-Bond TRACE Liquidity-to-ETF NAV Stress Transmission
**Status:** Proposed architecture only · **Specification:** [SPEC.md](./SPEC.md)

## Architecture
`source catalogs → license + availability validator → credit-trace-etf-nav-dislocation time-vintaged panel → feasible benchmark → candidate → independent economic replay → evidence ledger → human gate`

### A. Source adapters and data lineage
FINRA TRACE public aggregate/trade pages, subscription historical bond records, ETF market prices, NAV timestamps, bond indices, CDX basis. **Observation grain:** bond × disseminated trade timestamp × ETF NAV publication timestamp. **Decision horizon:** end-of-session / next-session ETF risk adjustment only; public aggregate data may not cover security-level historical panel.
**Public proxy adequacy:** FINRA explains TRACE reporting and offers public aggregates; institutional historical tick panels may require subscription.
Private inputs, if later approved, remain segregated and unavailable to public GitHub, Slack or public LLM prompts.

### B. Core baseline and model
- **Baseline first:** ETF realized volatility and quoted bid-ask spread.. Record every eligibility, cost and data-filter assumption.
- **Candidate:** Robust bond-liquidity dispersion index and ETF tracking-state model..
- **Advanced:** Structural ETF redemption/creation network with dealer intermediation bottlenecks.. Only attempt if candidate clears a preregistered incremental-complexity hurdle.
- **Objective:** LiquidityDisp_t=Q90(trade_cost_bond,t)-Q10(trade_cost_bond,t); predict |ETFprice_t-NAVestimate_t| with quote-timing controls
- **Variable meaning:** trade_cost_bond is valid time-matched cost proxy; NAVestimate is vendor methodology-specific, potentially stale and never treated as fillable.

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
Reported bond prices may be size-capped/delayed; TRACE trade access/licensing varies and NAV can embed stale marks.
Investigate whether a robust baseline or simpler model already achieves similar outcomes. Accept model abstention as a valid action when inputs are insufficient.

### F. Traceability and test matrix
REQ-001 → T-001,T-002; REQ-002 → T-003; REQ-003 → T-004,T-005; REQ-004 → T-006,T-007; NFR-001 → T-002,T-006; NFR-002 → T-001,T-008.
AC-001..AC-005 map to synthetic and holdout tests in [TASKS.md](./TASKS.md).

### G. Rollout
Public source feasibility → synthetic schema tests → licensed/approved actual data → costed backtest → shadow evaluation → human go/no-go; all downstream steps blocked until evidenced.
