# PLAN — Macro-Vintage Integrity Engine with Prediction Abstention
**Status:** Proposed architecture only · **Specification:** [SPEC.md](./SPEC.md)

## Architecture
`source catalogs → license + availability validator → macro-vintage-abstention-engine time-vintaged panel → feasible benchmark → candidate → independent economic replay → evidence ledger → human gate`

### A. Source adapters and data lineage
ALFRED historical revisions, ECB yield releases, OECD SDMX data vintage calendars, US/global market proxies. **Observation grain:** economic indicator × observation period × release date × vintage ID. **Decision horizon:** update only after first verified public release; revisions must enter as new events, not retroactively.
**Public proxy adequacy:** FRED real-time API explicitly supports known-as-of periods; series availability and revision dates require series-specific verification.
Private inputs, if later approved, remain segregated and unavailable to public GitHub, Slack or public LLM prompts.

### B. Core baseline and model
- **Baseline first:** Always-on macro momentum score built from latest-vintage series.. Record every eligibility, cost and data-filter assumption.
- **Candidate:** As-of macro feature store with release-confidence model and abstention..
- **Advanced:** Bayesian missing-data multiple-vintage filtering and conformal selective prediction with capacity-aware portfolio overlay.. Only attempt if candidate clears a preregistered incremental-complexity hurdle.
- **Objective:** Trade_t=1{E[utility(signal_t)|vintage_quality_t] > cost_t and quality_t>=q_min}; otherwise hold benchmark
- **Variable meaning:** quality measures source reliability, revision uncertainty, coverage and release history; expected utility estimated strictly from past vintages.

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
ALFRED historical series coverage, future revisions and OECD methodological breaks can be incomplete; abstention selection bias.
Investigate whether a robust baseline or simpler model already achieves similar outcomes. Accept model abstention as a valid action when inputs are insufficient.

### F. Traceability and test matrix
REQ-001 → T-001,T-002; REQ-002 → T-003; REQ-003 → T-004,T-005; REQ-004 → T-006,T-007; NFR-001 → T-002,T-006; NFR-002 → T-001,T-008.
AC-001..AC-005 map to synthetic and holdout tests in [TASKS.md](./TASKS.md).

### G. Rollout
Public source feasibility → synthetic schema tests → licensed/approved actual data → costed backtest → shadow evaluation → human go/no-go; all downstream steps blocked until evidenced.
