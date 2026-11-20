# TASKS — Securities-Lending Circular Flow Surveillance via Temporal Graphs
**All not started; completion must be evidenced.**
| Task | Description | Maps to | Definition of done |
|---|---|---|---|
| T-001 | Confirm legally feasible decision: Escalate suspicious short-lived circular borrow/return patterns for compliance review without inferring wrongdoing from volume alone. | REQ-001/AC-001 | Independent domain sign-off |
| T-002 | Define synthetic securities loan transfer edge × security × event timestamp and synthetic valid/invalid time fixtures | REQ-001,NFR-001 | Immutable schema + missing/late data failures |
| T-003 | Recreate costed benchmark: Two-party net-quantity turnaround rules | REQ-002/AC-002 | Deterministic unit tests and cost ledger |
| T-004 | Implement Temporal graph motif detection with exact deterministic event identity | REQ-003/AC-003 | Code, pinned config, deterministic seed |
| T-005 | Study Weakly supervised dynamic graph anomaly ranking with human-in-loop conformal calibration versus first candidate | REQ-003 | Preplanned ablation, no post-hoc switching |
| T-006 | Walk-forward out-of-sample test of Causal temporal-motif alerts improve precision at fixed review capacity over pairwise round-trip thresholds in seeded synthetic cases. | REQ-004/AC-004 | Independent holdout results, net-of-cost metrics |
| T-007 | Stress threat: False accusations, privileged customer data, and severe sample-selection bias in investigated cases. | REQ-004,NFR-001 | Placebo, bootstrap, capacity check |
| T-008 | Reviewer signoff, source license audit, conservative rollback | NFR-001,NFR-002/AC-005,AC-006 | Valid rights and human go/no-go |
## Proposed test IDs (not executed)
1. `test_seclending_circular_flow_surveillance_asof`
2. `test_seclending_circular_flow_surveillance_baseline`
3. `test_seclending_circular_flow_surveillance_negative`
4. `test_seclending_circular_flow_surveillance_rights`
**Done means tested engineering evidence, not just Markdown completion.**
