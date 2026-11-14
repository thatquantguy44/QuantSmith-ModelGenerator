# PLAN — Central-Bank Communication Semantic Surprise Across Languages
**Status:** Proposed architecture only · **Specification:** [SPEC.md](./SPEC.md)

## Architecture
`source catalogs → license + availability validator → central-bank-semantic-surprise time-vintaged panel → feasible benchmark → candidate → independent economic replay → evidence ledger → human gate`

### A. Source adapters and data lineage
Versioned official policy statements; actual publication timestamps; pre-event interest rate futures; FX and rates price bars; translated text audit. **Observation grain:** central-bank event × original language × statement version × publication timestamp. **Decision horizon:** after official statement becomes public; never permit news articles, transcripts or price reactions from after decision in input.
**Public proxy adequacy:** Official statements are public, but original-language versions, vintage snapshots and proprietary market expectations may need archival work.
Private inputs, if later approved, remain segregated and unavailable to public GitHub, Slack or public LLM prompts.

### B. Core baseline and model
- **Baseline first:** Policy rate surprise (or no-surprise dummy without licensed expectation) and prior-day rate changes.. Record every eligibility, cost and data-filter assumption.
- **Candidate:** Source-grounded claim-difference extractor with multilingual uncertainty and simple linear evaluation..
- **Advanced:** Constrained multilingual textual event state-space with calibration and abstention threshold.. Only attempt if candidate clears a preregistered incremental-complexity hurdle.
- **Objective:** Surprise_t = SentenceDistance(text_t, text_(t-1)) - ExpectedShift_t; alpha_(t+1)=β*Surprise_t, with abstention on low translation confidence
- **Variable meaning:** text_t is official published statement as of event; ExpectedShift requires pre-event expectations and is omitted if unavailable rather than inferred ex post.

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
Translation distortions, backfilled statement updates, and post-event news leakage are especially severe for multilingual event models.
Investigate whether a robust baseline or simpler model already achieves similar outcomes. Accept model abstention as a valid action when inputs are insufficient.

### F. Traceability and test matrix
REQ-001 → T-001,T-002; REQ-002 → T-003; REQ-003 → T-004,T-005; REQ-004 → T-006,T-007; NFR-001 → T-002,T-006; NFR-002 → T-001,T-008.
AC-001..AC-005 map to synthetic and holdout tests in [TASKS.md](./TASKS.md).

### G. Rollout
Public source feasibility → synthetic schema tests → licensed/approved actual data → costed backtest → shadow evaluation → human go/no-go; all downstream steps blocked until evidenced.
