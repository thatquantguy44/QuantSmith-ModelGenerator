# TASKS — Cyber-Outage Contingent Repo Funding Recovery Routes
**All not started; completion must be evidenced.**
| Task | Description | Maps to | Definition of done |
|---|---|---|---|
| T-001 | Confirm legally feasible decision: Pre-approve alternate cash-lender/clearing routes and reserve a minimum contingency liquidity buffer for an exogenous operational outage. | REQ-001/AC-001 | Independent domain sign-off |
| T-002 | Define route × lender class × hourly outage scenario and synthetic valid/invalid time fixtures | REQ-001,NFR-001 | Immutable schema + missing/late data failures |
| T-003 | Recreate costed benchmark: Fixed 10% contingency funding buffer with one permitted fallback | REQ-002/AC-002 | Deterministic unit tests and cost ledger |
| T-004 | Implement Two-stage robust multi-commodity flow with cyber failure scenarios | REQ-003/AC-003 | Code, pinned config, deterministic seed |
| T-005 | Study Distributionally robust scenario-tree route control with simultaneous correlated cash-lender disruptions versus first candidate | REQ-003 | Preplanned ablation, no post-hoc switching |
| T-006 | Walk-forward out-of-sample test of Conditional multi-route recovery decreases funding shortfall and expected disruption cost more than an equal-cost static backup buffer. | REQ-004/AC-004 | Independent holdout results, net-of-cost metrics |
| T-007 | Stress threat: Public aggregates cannot recover the bank-level cash-lender network or prove an actual route is legally available. | REQ-004,NFR-001 | Placebo, bootstrap, capacity check |
| T-008 | Reviewer signoff, source license audit, conservative rollback | NFR-001,NFR-002/AC-005,AC-006 | Valid rights and human go/no-go |
## Proposed test IDs (not executed)
1. `test_repo_cyber_funding_recovery_asof`
2. `test_repo_cyber_funding_recovery_baseline`
3. `test_repo_cyber_funding_recovery_negative`
4. `test_repo_cyber_funding_recovery_rights`
**Done means tested engineering evidence, not just Markdown completion.**
