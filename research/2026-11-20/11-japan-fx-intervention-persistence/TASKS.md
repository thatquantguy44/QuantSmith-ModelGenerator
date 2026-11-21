# TASKS — Japan FX Intervention Impact and Option-Skew Persistence
**All not started; completion must be evidenced.**
| Task | Description | Maps to | Definition of done |
|---|---|---|---|
| T-001 | Confirm legally feasible decision: Determine when to reduce/hedge yen exposure following **publicly observed** intervention or subsequent official disclosure. | REQ-001/AC-001 | Independent domain sign-off |
| T-002 | Define intervention disclosure event × FX option tenor × quote timestamp and synthetic valid/invalid time fixtures | REQ-001,NFR-001 | Immutable schema + missing/late data failures |
| T-003 | Recreate costed benchmark: Standard spot momentum and monetary-policy announcement dummy | REQ-002/AC-002 | Deterministic unit tests and cost ledger |
| T-004 | Implement Disclosure-timestamp event study with matched controls and local projections | REQ-003/AC-003 | Code, pinned config, deterministic seed |
| T-005 | Study Partial-identification causal synthetic control separating information, execution and portfolio-flow channels versus first candidate | REQ-003 | Preplanned ablation, no post-hoc switching |
| T-006 | Walk-forward out-of-sample test of A release-time-corrected intervention-event measure predicts conditional 1–20-day FX variance/skew adjustment beyond macro announcements and momentum. | REQ-004/AC-004 | Independent holdout results, net-of-cost metrics |
| T-007 | Stress threat: Actual intervention execution is not transparently known in real time; small event count undermines causal certainty. | REQ-004,NFR-001 | Placebo, bootstrap, capacity check |
| T-008 | Reviewer signoff, source license audit, conservative rollback | NFR-001,NFR-002/AC-005,AC-006 | Valid rights and human go/no-go |
## Proposed test IDs (not executed)
1. `test_japan_fx_intervention_persistence_asof`
2. `test_japan_fx_intervention_persistence_baseline`
3. `test_japan_fx_intervention_persistence_negative`
4. `test_japan_fx_intervention_persistence_rights`
**Done means tested engineering evidence, not just Markdown completion.**
