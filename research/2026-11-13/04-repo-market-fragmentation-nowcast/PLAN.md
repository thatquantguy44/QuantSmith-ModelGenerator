# PLAN — Cleared Versus Tri-Party Repo Fragmentation Nowcast
**Status:** Proposed architecture only · **Specification:** [SPEC.md](./SPEC.md)

## Architecture
`source catalogs → license + availability validator → repo-market-fragmentation-nowcast time-vintaged panel → feasible benchmark → candidate → independent economic replay → evidence ledger → human gate`

### A. Source adapters and data lineage
OFR cleared and tri-party rate-volume series; collateral categories; SOFR; weekly dealer aggregate financing; release metadata. **Observation grain:** venue × collateral class × tenor × underlying observation date, plus public publication timestamp. **Decision horizon:** risk update only after OFR release; cleared repo T+1 and tri-party T+2 availability; never use same-day unpublished values.
**Public proxy adequacy:** OFR reports secured funding data with documented one- and two-day publication lags and confidentiality blanks.
Private inputs, if later approved, remain segregated and unavailable to public GitHub, Slack or public LLM prompts.

### B. Core baseline and model
- **Baseline first:** SOFR level change and aggregate funding volume z-score.. Record every eligibility, cost and data-filter assumption.
- **Candidate:** State-space latent fragmentation index with lag-aware missingness..
- **Advanced:** Hierarchical online change-point and causal regime attribution by venue and reporting channel.. Only attempt if candidate clears a preregistered incremental-complexity hurdle.
- **Objective:** F_t=Σ_v ω_v (r_v,t-r_ref,t)^2 + η*HHI(volume_v,t); predict P(stress_(t+1)|F_<=t, publication_lags)
- **Variable meaning:** v indexes funding venue/tenor/collateral categories; weights ω_v normalize liquidity; η calibrates volume concentration penalty.

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
Revised/missing suppressed OFR cells and cross-venue holiday timing can create lookahead and artificial divergences.
Investigate whether a robust baseline or simpler model already achieves similar outcomes. Accept model abstention as a valid action when inputs are insufficient.

### F. Traceability and test matrix
REQ-001 → T-001,T-002; REQ-002 → T-003; REQ-003 → T-004,T-005; REQ-004 → T-006,T-007; NFR-001 → T-002,T-006; NFR-002 → T-001,T-008.
AC-001..AC-005 map to synthetic and holdout tests in [TASKS.md](./TASKS.md).

### G. Rollout
Public source feasibility → synthetic schema tests → licensed/approved actual data → costed backtest → shadow evaluation → human go/no-go; all downstream steps blocked until evidenced.
