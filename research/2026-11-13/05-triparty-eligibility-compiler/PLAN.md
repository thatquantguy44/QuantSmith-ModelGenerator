# PLAN — Tri-Party Collateral Eligibility Clause-to-Constraint Compiler
**Status:** Proposed architecture only · **Specification:** [SPEC.md](./SPEC.md)

## Architecture
`source catalogs → license + availability validator → triparty-eligibility-compiler time-vintaged panel → feasible benchmark → candidate → independent economic replay → evidence ledger → human gate`

### A. Source adapters and data lineage
Synthetic collateral schedules; asset master; rating/issuer; eligibility categories; haircut tables; human-labeled clause examples. **Observation grain:** contract clause × effective version × collateral asset × valuation time. **Decision horizon:** rules valid at collateral decision; amendments apply from legal effective date, not document creation date.
**Public proxy adequacy:** Public clearing and securities-financing guidance gives domain patterns but not private triparty legal schedules.
Private inputs, if later approved, remain segregated and unavailable to public GitHub, Slack or public LLM prompts.

### B. Core baseline and model
- **Baseline first:** Rule tables hand-transcribed and checked by two human operators.. Record every eligibility, cost and data-filter assumption.
- **Candidate:** Schema-constrained text extraction with symbolic eligibility evaluation and abstention..
- **Advanced:** Contradiction-aware graph of rule amendments with formal test generation and reviewer feedback.. Only attempt if candidate clears a preregistered incremental-complexity hurdle.
- **Objective:** maximize Σ_(i,j) value_i*x_ij - substitution_cost_ij; x_ij<=eligible_ij; Σ_i exposure_ij<=limit_j
- **Variable meaning:** x_ij is amount of asset i allocated to collateral agreement j; eligible_ij is verified legal rule, not an LLM prediction.

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
Natural-language ambiguity, contract precedence and jurisdiction-specific clauses make full automation unsafe.
Investigate whether a robust baseline or simpler model already achieves similar outcomes. Accept model abstention as a valid action when inputs are insufficient.

### F. Traceability and test matrix
REQ-001 → T-001,T-002; REQ-002 → T-003; REQ-003 → T-004,T-005; REQ-004 → T-006,T-007; NFR-001 → T-002,T-006; NFR-002 → T-001,T-008.
AC-001..AC-005 map to synthetic and holdout tests in [TASKS.md](./TASKS.md).

### G. Rollout
Public source feasibility → synthetic schema tests → licensed/approved actual data → costed backtest → shadow evaluation → human go/no-go; all downstream steps blocked until evidenced.
