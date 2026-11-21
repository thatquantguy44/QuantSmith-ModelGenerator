# TASKS — CCP Default-Fund Mutualization Marginal Risk Budget
**All not started; completion must be evidenced.**
| Task | Description | Maps to | Definition of done |
|---|---|---|---|
| T-001 | Confirm legally feasible decision: Set internal clearing exposure budgets based on potential default-fund replenishment and contingent mutualized-loss allocation. | REQ-001/AC-001 | Independent domain sign-off |
| T-002 | Define CCP membership × cleared product × default stress scenario and synthetic valid/invalid time fixtures | REQ-001,NFR-001 | Immutable schema + missing/late data failures |
| T-003 | Recreate costed benchmark: Exposure limit proportional to initial margin only | REQ-002/AC-002 | Deterministic unit tests and cost ledger |
| T-004 | Implement Transparent worst-two-member default waterfall simulator | REQ-003/AC-003 | Code, pinned config, deterministic seed |
| T-005 | Study Coherent-risk allocation via Shapley/gradient ES under correlated default network scenarios versus first candidate | REQ-003 | Preplanned ablation, no post-hoc switching |
| T-006 | Walk-forward out-of-sample test of A conservative tail contribution metric improves risk-adjusted clearing exposure allocation against nominal balance or posted-margin controls. | REQ-004/AC-004 | Independent holdout results, net-of-cost metrics |
| T-007 | Stress threat: Actual default fund contributions and replenishment terms may differ from public examples and vary by venue. | REQ-004,NFR-001 | Placebo, bootstrap, capacity check |
| T-008 | Reviewer signoff, source license audit, conservative rollback | NFR-001,NFR-002/AC-005,AC-006 | Valid rights and human go/no-go |
## Proposed test IDs (not executed)
1. `test_ccp_default_fund_tail_budget_asof`
2. `test_ccp_default_fund_tail_budget_baseline`
3. `test_ccp_default_fund_tail_budget_negative`
4. `test_ccp_default_fund_tail_budget_rights`
**Done means tested engineering evidence, not just Markdown completion.**
