# PLAN — Securities-Lending Fee Observability & Selection-Bias Corrector
**Status:** Proposed architecture only · **Specification:** [SPEC.md](./SPEC.md)

## Architecture
`source catalogs → license + availability validator → lending-fee-selection-debiasing time-vintaged panel → feasible benchmark → candidate → independent economic replay → evidence ledger → human gate`

### A. Source adapters and data lineage
Contributed executed fee samples; public security volume/short-interest proxies; locate response metadata; source coverage and revisions. **Observation grain:** security × lending day × vendor/contributor population. **Decision horizon:** benchmark at next published cutoff; never use end-of-day contributions before receipt.
**Public proxy adequacy:** Public security market data can inform context, but no complete free securities-loan execution tape is assumed.
Private inputs, if later approved, remain segregated and unavailable to public GitHub, Slack or public LLM prompts.

### B. Core baseline and model
- **Baseline first:** Daily equally weighted or outstanding-value-weighted observed market fees.. Record every eligibility, cost and data-filter assumption.
- **Candidate:** Doubly robust weighting with overlap and selection-sensitivity intervals..
- **Advanced:** Bayesian selection model with unverifiable missing-not-at-random stress bounds.. Only attempt if candidate clears a preregistered incremental-complexity hurdle.
- **Objective:** mu_hat = Σ_i w_i*y_i/Σ_i w_i; w_i=1/P(observed_i|X_i); report sensitivity to unidentified selection
- **Variable meaning:** y_i is observed fee; X_i observable security/liquidity/context; propensity weights are estimated from an externally validated sample frame.

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
Missing-not-at-random selection cannot be identified from executed loans alone; confidence intervals can be falsely narrow.
Investigate whether a robust baseline or simpler model already achieves similar outcomes. Accept model abstention as a valid action when inputs are insufficient.

### F. Traceability and test matrix
REQ-001 → T-001,T-002; REQ-002 → T-003; REQ-003 → T-004,T-005; REQ-004 → T-006,T-007; NFR-001 → T-002,T-006; NFR-002 → T-001,T-008.
AC-001..AC-005 map to synthetic and holdout tests in [TASKS.md](./TASKS.md).

### G. Rollout
Public source feasibility → synthetic schema tests → licensed/approved actual data → costed backtest → shadow evaluation → human go/no-go; all downstream steps blocked until evidenced.
