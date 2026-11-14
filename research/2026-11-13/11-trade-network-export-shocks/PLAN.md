# PLAN — Trade-Network Export-Shock Transmission to Equity Sectors
**Status:** Proposed architecture only · **Specification:** [SPEC.md](./SPEC.md)

## Architecture
`source catalogs → license + availability validator → trade-network-export-shocks time-vintaged panel → feasible benchmark → candidate → independent economic replay → evidence ledger → human gate`

### A. Source adapters and data lineage
UN Comtrade reported and partner-reported trade by HS code/month; sector country revenue mix; FX; sector returns and macro controls. **Observation grain:** reporter × partner × HS code × reference month × publication/availability timestamp. **Decision horizon:** monthly after trade report publication and revision; NEVER trade at reference-month timestamp.
**Public proxy adequacy:** UN Comtrade public preview has limited records; full historical coverage may require free keyed or premium bulk access.
Private inputs, if later approved, remain segregated and unavailable to public GitHub, Slack or public LLM prompts.

### B. Core baseline and model
- **Baseline first:** Equal-weight country sector allocation with FX and local industrial production controls.. Record every eligibility, cost and data-filter assumption.
- **Candidate:** Sparse directed trade graph factor with event-lag-aware regressions..
- **Advanced:** Causal graph neural propagation with hard release-vintage masking and sector earnings transmission.. Only attempt if candidate clears a preregistered incremental-complexity hurdle.
- **Objective:** Shock_(c,k,t)=Σ_p upstream_weight_(c,k,p)*Δexports_(p,t); alpha_(sector,t+h)=β*Shock_available_t - controls
- **Variable meaning:** c is country, k sector, p harmonized product/trade edge, h a preselected post-publication investment horizon.

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
Revisions, late reporters, trade re-exports and mapping HS codes to listed firms can create survivorship and spurious exposure.
Investigate whether a robust baseline or simpler model already achieves similar outcomes. Accept model abstention as a valid action when inputs are insufficient.

### F. Traceability and test matrix
REQ-001 → T-001,T-002; REQ-002 → T-003; REQ-003 → T-004,T-005; REQ-004 → T-006,T-007; NFR-001 → T-002,T-006; NFR-002 → T-001,T-008.
AC-001..AC-005 map to synthetic and holdout tests in [TASKS.md](./TASKS.md).

### G. Rollout
Public source feasibility → synthetic schema tests → licensed/approved actual data → costed backtest → shadow evaluation → human go/no-go; all downstream steps blocked until evidenced.
