# TASKS — Evergreen Repo Early-Termination Optionality Risk Budget
**All not started; completion must be evidenced.**
| Task | Description | Maps to | Definition of done |
|---|---|---|---|
| T-001 | Confirm legally feasible decision: Set rate/tenor risk charges for unilateral termination and extension rights in open repo or evergreen funding. | REQ-001/AC-001 | Independent domain sign-off |
| T-002 | Define contract × notice period × funding day × interest-rate state and synthetic valid/invalid time fixtures | REQ-001,NFR-001 | Immutable schema + missing/late data failures |
| T-003 | Recreate costed benchmark: Static repo spread plus deterministic notice-day funding reserve | REQ-002/AC-002 | Deterministic unit tests and cost ledger |
| T-004 | Implement Least-squares Monte Carlo for bilateral asymmetric stop decisions | REQ-003/AC-003 | Code, pinned config, deterministic seed |
| T-005 | Study Nonzero-sum stochastic game with liquidity-dependent termination intensities versus first candidate | REQ-003 | Preplanned ablation, no post-hoc switching |
| T-006 | Walk-forward out-of-sample test of Notice-option-adjusted funding pricing reduces out-of-sample replacement-cost surprises versus duration-only term curve cost. | REQ-004/AC-004 | Independent holdout results, net-of-cost metrics |
| T-007 | Stress threat: Non-observed counterparty exercise behavior; public term repo alone does not identify proprietary notice clauses. | REQ-004,NFR-001 | Placebo, bootstrap, capacity check |
| T-008 | Reviewer signoff, source license audit, conservative rollback | NFR-001,NFR-002/AC-005,AC-006 | Valid rights and human go/no-go |
## Proposed test IDs (not executed)
1. `test_evergreen_repo_termination_option_asof`
2. `test_evergreen_repo_termination_option_baseline`
3. `test_evergreen_repo_termination_option_negative`
4. `test_evergreen_repo_termination_option_rights`
**Done means tested engineering evidence, not just Markdown completion.**
