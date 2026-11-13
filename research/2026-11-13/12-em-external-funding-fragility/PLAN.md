# PLAN — EM External-Funding Fragility via Currency Mismatch and IIP
**Status:** Proposed architecture only · **Specification:** [SPEC.md](./SPEC.md)

## Architecture
`source catalogs → license + availability validator → em-external-funding-fragility time-vintaged panel → feasible benchmark → candidate → independent economic replay → evidence ledger → human gate`

### A. Source adapters and data lineage
IMF IIP, BIS global liquidity quarterly FX credit, OECD macro where available, public reserve series and FX/sovereign returns. **Observation grain:** country × reporting quarter × first-public-availability time. **Decision horizon:** quarterly risk changes after actual statistical release; never refresh historic positions with today's revised values.
**Public proxy adequacy:** BIS GLI and IMF IIP published quarterly with varying country coverage and revisions.
Private inputs, if later approved, remain segregated and unavailable to public GitHub, Slack or public LLM prompts.

### B. Core baseline and model
- **Baseline first:** Traditional sovereign credit rating tier, FX carry and three-month realized volatility.. Record every eligibility, cost and data-filter assumption.
- **Candidate:** Point-in-time standardized funding mismatch factor with recession/regime interactions..
- **Advanced:** Joint skewed macro-financial state-space with robust optimization and missing vintage uncertainty.. Only attempt if candidate clears a preregistered incremental-complexity hurdle.
- **Objective:** Fragility_c,t=(FX_credit_c,t - liquid_FX_assets_c,t)/GDP_c,t + λ*short_debt_service_c,t; optimize w for worst-case loss
- **Variable meaning:** c denotes country; all stocks denominated in comparable FX units; FX-credit and external-assets proxies can have incompatible reporting definitions requiring explicit normalization.

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
Global liquidity metrics are quarterly; imputed weekly updates are model estimates, not observations.
Investigate whether a robust baseline or simpler model already achieves similar outcomes. Accept model abstention as a valid action when inputs are insufficient.

### F. Traceability and test matrix
REQ-001 → T-001,T-002; REQ-002 → T-003; REQ-003 → T-004,T-005; REQ-004 → T-006,T-007; NFR-001 → T-002,T-006; NFR-002 → T-001,T-008.
AC-001..AC-005 map to synthetic and holdout tests in [TASKS.md](./TASKS.md).

### G. Rollout
Public source feasibility → synthetic schema tests → licensed/approved actual data → costed backtest → shadow evaluation → human go/no-go; all downstream steps blocked until evidenced.
