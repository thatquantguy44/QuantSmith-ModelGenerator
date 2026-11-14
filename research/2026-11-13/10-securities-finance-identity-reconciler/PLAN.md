# PLAN — Cross-Book Securities Finance Identity Reconciliation Graph
**Status:** Proposed architecture only · **Specification:** [SPEC.md](./SPEC.md)

## Architecture
`source catalogs → license + availability validator → securities-finance-identity-reconciler time-vintaged panel → feasible benchmark → candidate → independent economic replay → evidence ledger → human gate`

### A. Source adapters and data lineage
Synthetic records containing lifecycle events, ISIN/CUSIP, product type, settlement date, amount, counterparty alias and amendment chain. **Observation grain:** source record × canonical candidate × event version × timestamp. **Decision horizon:** real-time/overnight reconciliation; no future correction can be applied retroactively to a prior risk snapshot.
**Public proxy adequacy:** Official definitions guide field semantics, but real records remain private; publish only synthetic fixtures.
Private inputs, if later approved, remain segregated and unavailable to public GitHub, Slack or public LLM prompts.

### B. Core baseline and model
- **Baseline first:** Exact ID join plus manually triaged fuzzy-name matches.. Record every eligibility, cost and data-filter assumption.
- **Candidate:** Bipartite deterministic matching with hard identity constraints and provenance..
- **Advanced:** Human-review active-learning on uncertain clusters with error budget and privacy-preserving synthetic tests.. Only attempt if candidate clears a preregistered incremental-complexity hurdle.
- **Objective:** min_M Σ_(i,j) c_ij*M_ij + λ*unmatched(M); M_ij∈{0,1}, one-to-one constraints and incompatible identifier rules
- **Variable meaning:** M_ij selects a candidate match between external and canonical records; c_ij is audited mismatch cost with hard ID prohibitions.

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
LLM or probabilistic model can silently merge legally distinct entities or settlement legs.
Investigate whether a robust baseline or simpler model already achieves similar outcomes. Accept model abstention as a valid action when inputs are insufficient.

### F. Traceability and test matrix
REQ-001 → T-001,T-002; REQ-002 → T-003; REQ-003 → T-004,T-005; REQ-004 → T-006,T-007; NFR-001 → T-002,T-006; NFR-002 → T-001,T-008.
AC-001..AC-005 map to synthetic and holdout tests in [TASKS.md](./TASKS.md).

### G. Rollout
Public source feasibility → synthetic schema tests → licensed/approved actual data → costed backtest → shadow evaluation → human go/no-go; all downstream steps blocked until evidenced.
