# TASKS — Reg SHO Locate Evidence and Borrow-Capacity Audit Engine
**All not started; completion must be evidenced.**
| Task | Description | Maps to | Definition of done |
|---|---|---|---|
| T-001 | Confirm legally feasible decision: Block or escalate a short-sale request if contemporaneous legally qualifying locate evidence or remaining documented quantity is insufficient. | REQ-001/AC-001 | Independent domain sign-off |
| T-002 | Define short-sale request × account × security × source × event timestamp and synthetic valid/invalid time fixtures | REQ-001,NFR-001 | Immutable schema + missing/late data failures |
| T-003 | Recreate costed benchmark: End-of-day deterministic locate exception SQL rules | REQ-002/AC-002 | Deterministic unit tests and cost ledger |
| T-004 | Implement Typed event-sourcing finite-state verification with causal explainability | REQ-003/AC-003 | Code, pinned config, deterministic seed |
| T-005 | Study Conformal anomaly scoring for ambiguous evidence routed to human review, never autonomous compliance override versus first candidate | REQ-003 | Preplanned ablation, no post-hoc switching |
| T-006 | Walk-forward out-of-sample test of Event-sourced evidence reconstruction detects noncompliant or capacity-exhausted locates earlier than end-of-day exception review without excess false rejects. | REQ-004/AC-004 | Independent holdout results, net-of-cost metrics |
| T-007 | Stress threat: Reg SHO exemptions, broker responsibilities and settlement rules require qualified legal interpretation. | REQ-004,NFR-001 | Placebo, bootstrap, capacity check |
| T-008 | Reviewer signoff, source license audit, conservative rollback | NFR-001,NFR-002/AC-005,AC-006 | Valid rights and human go/no-go |
## Proposed test IDs (not executed)
1. `test_short_locate_evidence_audit_asof`
2. `test_short_locate_evidence_audit_baseline`
3. `test_short_locate_evidence_audit_negative`
4. `test_short_locate_evidence_audit_rights`
**Done means tested engineering evidence, not just Markdown completion.**
