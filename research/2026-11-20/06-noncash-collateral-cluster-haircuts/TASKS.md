# TASKS — Noncash Collateral Correlation-Cluster Haircut Controller
**All not started; completion must be evidenced.**
| Task | Description | Maps to | Definition of done |
|---|---|---|---|
| T-001 | Confirm legally feasible decision: Recommend minimum defensive haircuts for a collateral basket based on joint concentration and liquidation correlation. | REQ-001/AC-001 | Independent domain sign-off |
| T-002 | Define collateral security × issuer cluster × loan exposure × as-of time and synthetic valid/invalid time fixtures | REQ-001,NFR-001 | Immutable schema + missing/late data failures |
| T-003 | Recreate costed benchmark: Uniform issuer/asset-class static haircut | REQ-002/AC-002 | Deterministic unit tests and cost ledger |
| T-004 | Implement Scenario CVaR optimization with issuer cluster caps | REQ-003/AC-003 | Code, pinned config, deterministic seed |
| T-005 | Study Distributionally robust ambiguity-set CVaR with wrong-way liquidity correlation versus first candidate | REQ-003 | Preplanned ablation, no post-hoc switching |
| T-006 | Walk-forward out-of-sample test of Cluster-aware chance constraints produce lower stressed shortfall than sector-flat haircuts at a matched average financing cost. | REQ-004/AC-004 | Independent holdout results, net-of-cost metrics |
| T-007 | Stress threat: Asset covariance may break exactly when haircuts are needed and public free-float proxies omit liquidation controls. | REQ-004,NFR-001 | Placebo, bootstrap, capacity check |
| T-008 | Reviewer signoff, source license audit, conservative rollback | NFR-001,NFR-002/AC-005,AC-006 | Valid rights and human go/no-go |
## Proposed test IDs (not executed)
1. `test_noncash_collateral_cluster_haircuts_asof`
2. `test_noncash_collateral_cluster_haircuts_baseline`
3. `test_noncash_collateral_cluster_haircuts_negative`
4. `test_noncash_collateral_cluster_haircuts_rights`
**Done means tested engineering evidence, not just Markdown completion.**
