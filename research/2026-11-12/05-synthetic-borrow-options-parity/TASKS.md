# TASKS — Synthetic Borrow Supply via Options Parity
**All tasks not started.** Completion requires human-reviewed evidence, tests and documented costs.
| ID | Work item | Trace | Definition of done |
|---|---|---|---|
| T-001 | Confirm hypothesis, data rights and eligibility | REQ-001,NFR-002 | Source and legal review approved |
| T-002 | Build point-in-time event schema and synthetic fixtures | REQ-001,NFR-001,AC-001 | Rejects leakage, duplicates, impossible states |
| T-003 | Implement physical borrow only | REQ-002,AC-002 | Reproducible baseline economics and cost tests |
| T-004 | Implement implied financing via corrected put-call parity | REQ-003 | Deterministic candidate with pinned settings |
| T-005 | Assess mixed-integer derivative replication with exercise constraints only if justified | REQ-003 | Ablation and complexity justification |
| T-006 | Paired economic holdout evaluation | REQ-004,AC-003 | Same opportunities, total costs and no leakage |
| T-007 | Stress American exercise and forecast-dividend mismatch | REQ-004,AC-004 | Robustness and metric report: executable financing benefit, hedge error, margin and basis risk |
| T-008 | Review entitlement and shadow-mode gates | NFR-002,AC-005 | Human signoff, no automatic trading |
## Test coverage map
AC-001→`test_pit_schema`; AC-002→`test_baseline_costs`; AC-003→`test_policy_holdout`; AC-004→`test_tail_and_capacity`; AC-005→`test_source_rights`. **Tests are proposed, not implemented.**
