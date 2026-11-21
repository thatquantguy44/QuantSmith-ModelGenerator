# TASKS — European CSDR Penalty-Aware Settlement Queue Prioritization
**All not started; completion must be evidenced.**
| Task | Description | Maps to | Definition of done |
|---|---|---|---|
| T-001 | Confirm legally feasible decision: Prioritize settlement instructions under explicit penalty eligibility and scarce processing resources. | REQ-001/AC-001 | Independent domain sign-off |
| T-002 | Define instruction × CSD × ISIN × intended settlement day × decision time and synthetic valid/invalid time fixtures | REQ-001,NFR-001 | Immutable schema + missing/late data failures |
| T-003 | Recreate costed benchmark: FIFO or largest-notional-first allowed settlement priority | REQ-002/AC-002 | Deterministic unit tests and cost ledger |
| T-004 | Implement Constrained weighted-shortest-processing-time queue policy with eligibility rules | REQ-003/AC-003 | Code, pinned config, deterministic seed |
| T-005 | Study Approximate dynamic programming under stochastic matched delivery arrival times versus first candidate | REQ-003 | Preplanned ablation, no post-hoc switching |
| T-006 | Walk-forward out-of-sample test of A rule-aware queue policy lowers expected daily penalties and fail duration without worsening operational priority controls relative to FIFO. | REQ-004/AC-004 | Independent holdout results, net-of-cost metrics |
| T-007 | Stress threat: Misclassification of non-attributable fail causes or legal exclusion yields incorrect optimized queues. | REQ-004,NFR-001 | Placebo, bootstrap, capacity check |
| T-008 | Reviewer signoff, source license audit, conservative rollback | NFR-001,NFR-002/AC-005,AC-006 | Valid rights and human go/no-go |
## Proposed test IDs (not executed)
1. `test_eu_csdr_penalty_queue_policy_asof`
2. `test_eu_csdr_penalty_queue_policy_baseline`
3. `test_eu_csdr_penalty_queue_policy_negative`
4. `test_eu_csdr_penalty_queue_policy_rights`
**Done means tested engineering evidence, not just Markdown completion.**
