# PLAN — Treasury Clearing Access-Path & Duplicate-Margin Optimizer
**Status:** Proposed architecture only · **Specification:** [SPEC.md](./SPEC.md)

## Architecture
`source catalogs → license + availability validator → clearing-access-duplicate-margin time-vintaged panel → feasible benchmark → candidate → independent economic replay → evidence ledger → human gate`

### A. Source adapters and data lineage
Eligible trade templates; path availability; historical quote spreads; initial/variation margin stress; capital/CCLF allocation; modeled netting sets; direct/sponsored/agent fees. **Observation grain:** trade × eligible clearing access path × decision timestamp. **Decision horizon:** trade routing decision at quote acceptance; historical public aggregates are lagged and cannot be used as intraday quotes.
**Public proxy adequacy:** SEC and DTCC rules describe access but do not provide participant-specific margin or allocation cost.
Private inputs, if later approved, remain segregated and unavailable to public GitHub, Slack or public LLM prompts.

### B. Core baseline and model
- **Baseline first:** Minimize executable repo rate ignoring path-specific costs, after validating that every route is eligible.. Record every eligibility, cost and data-filter assumption.
- **Candidate:** Mixed-integer convex routing with separate margin, settlement and liquidity shadow prices..
- **Advanced:** Stochastic two-stage CCP-margin and default-fund planning with cross-netting robustness.. Only attempt if candidate clears a preregistered incremental-complexity hurdle.
- **Objective:** min_(x_p) Σ_p x_p*(rate_p*notional*T + fee_p + margin_carry_p + default_fund_p + cclf_liquidity_p) - verified_netting_benefit(x); Σ_p x_p=1; x_p=0 for ineligible paths
- **Variable meaning:** x_p is fraction routed through path p; T is year-fraction tenor; margin, default fund, CCLF and netting effects use validated path-specific rules rather than assumed offsets.

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
Clearing rule exemptions and netting eligibility vary; estimated margin offsets could be nonportable across entities.
Investigate whether a robust baseline or simpler model already achieves similar outcomes. Accept model abstention as a valid action when inputs are insufficient.

### F. Traceability and test matrix
REQ-001 → T-001,T-002; REQ-002 → T-003; REQ-003 → T-004,T-005; REQ-004 → T-006,T-007; NFR-001 → T-002,T-006; NFR-002 → T-001,T-008.
AC-001..AC-005 map to synthetic and holdout tests in [TASKS.md](./TASKS.md).

### G. Rollout
Public source feasibility → synthetic schema tests → licensed/approved actual data → costed backtest → shadow evaluation → human go/no-go; all downstream steps blocked until evidenced.
