# PLAN — Manufactured-Dividend and Corporate-Action Loan Economics
**Status:** Proposed architecture only · **Specification:** [SPEC.md](./SPEC.md)

## Architecture
`source catalogs → license + availability validator → manufactured-dividend-corporate-actions time-vintaged panel → feasible benchmark → candidate → independent economic replay → evidence ledger → human gate`

### A. Source adapters and data lineage
Ex/record/pay dates; loan life; fee accrual; event elections; dividend amounts; owner tax flags and permitted return/recall rules. **Observation grain:** security × beneficial owner program × corporate-action event × decision timestamp. **Decision horizon:** event decisions before ex-date cutoff, using only announced corporate actions and approved tax interpretations then available.
**Public proxy adequacy:** Public filings can anchor event timelines, but loan, tax and owner entitlement data are nonpublic.
Private inputs, if later approved, remain segregated and unavailable to public GitHub, Slack or public LLM prompts.

### B. Core baseline and model
- **Baseline first:** Renew if lending fee remains positive and return only upon explicit mandatory recall.. Record every eligibility, cost and data-filter assumption.
- **Candidate:** Rule-checked event economics and constrained loan life-cycle integer optimizer..
- **Advanced:** Scenario tree for unresolved election announcements and corporate action adjustment ranges.. Only attempt if candidate clears a preregistered incremental-complexity hurdle.
- **Objective:** max_(a in eligible_actions) [fee(a)-manufactured_payment_adjustment(a)-corporate_action_cost(a)-recall_cost(a)-tax_adjustment(a)]
- **Variable meaning:** a is a legally permitted loan lifecycle action; each component is booked at the owner-specific event date and in consistent after-tax units.

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
Tax withholding, treaty benefits and manufactured-dividend treatment cannot be assumed from issuer-country information alone.
Investigate whether a robust baseline or simpler model already achieves similar outcomes. Accept model abstention as a valid action when inputs are insufficient.

### F. Traceability and test matrix
REQ-001 → T-001,T-002; REQ-002 → T-003; REQ-003 → T-004,T-005; REQ-004 → T-006,T-007; NFR-001 → T-002,T-006; NFR-002 → T-001,T-008.
AC-001..AC-005 map to synthetic and holdout tests in [TASKS.md](./TASKS.md).

### G. Rollout
Public source feasibility → synthetic schema tests → licensed/approved actual data → costed backtest → shadow evaluation → human go/no-go; all downstream steps blocked until evidenced.
