# TASKS — Global Shipping Connectivity Re-Routing to Inflation and Equity Margins
**All not started; completion must be evidenced.**
| Task | Description | Maps to | Definition of done |
|---|---|---|---|
| T-001 | Confirm legally feasible decision: Size logistics/inflation hedges when public route connectivity and port-service centrality shift. | REQ-001/AC-001 | Independent domain sign-off |
| T-002 | Define country/port route × monthly index release × subsequent inflation/earnings outcome and synthetic valid/invalid time fixtures | REQ-001,NFR-001 | Immutable schema + missing/late data failures |
| T-003 | Recreate costed benchmark: Aggregate global shipping index versus region CPI with fixed lag | REQ-002/AC-002 | Deterministic unit tests and cost ledger |
| T-004 | Implement Supply-route network exposure local projections | REQ-003/AC-003 | Code, pinned config, deterministic seed |
| T-005 | Study Causal graph shock transmission with endogenous alternative route capacity and measurement error versus first candidate | REQ-003 | Preplanned ablation, no post-hoc switching |
| T-006 | Walk-forward out-of-sample test of Route-centrality-adjusted connectivity changes improve delayed goods-inflation and shipper-margin forecasts over raw container volume. | REQ-004/AC-004 | Independent holdout results, net-of-cost metrics |
| T-007 | Stress threat: Connectivity is not real-time port congestion and quarterly updates can obscure freight cycle timing. | REQ-004,NFR-001 | Placebo, bootstrap, capacity check |
| T-008 | Reviewer signoff, source license audit, conservative rollback | NFR-001,NFR-002/AC-005,AC-006 | Valid rights and human go/no-go |
## Proposed test IDs (not executed)
1. `test_global_port_connectivity_inflation_asof`
2. `test_global_port_connectivity_inflation_baseline`
3. `test_global_port_connectivity_inflation_negative`
4. `test_global_port_connectivity_inflation_rights`
**Done means tested engineering evidence, not just Markdown completion.**
