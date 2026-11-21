# TASKS — ETF Creation/Redemption Basket Shock to Stock-Loan Supply
**All not started; completion must be evidenced.**
| Task | Description | Maps to | Definition of done |
|---|---|---|---|
| T-001 | Confirm legally feasible decision: Reserve lendable constituent supply ahead of known or forecasted ETF in-kind redemption/creation windows. | REQ-001/AC-001 | Independent domain sign-off |
| T-002 | Define ETF × constituent × creation/redemption day × publication time and synthetic valid/invalid time fixtures | REQ-001,NFR-001 | Immutable schema + missing/late data failures |
| T-003 | Recreate costed benchmark: Change in ETF shares outstanding plus index-event dummy | REQ-002/AC-002 | Deterministic unit tests and cost ledger |
| T-004 | Implement Hierarchical event study with issuer-basket aggregation and controls | REQ-003/AC-003 | Code, pinned config, deterministic seed |
| T-005 | Study Instrumented flow shock model addressing ETF price-demand endogeneity versus first candidate | REQ-003 | Preplanned ablation, no post-hoc switching |
| T-006 | Walk-forward out-of-sample test of Point-in-time basket-flow measures predict incremental short-horizon available-to-lend changes beyond conventional index membership and short-interest proxies. | REQ-004/AC-004 | Independent holdout results, net-of-cost metrics |
| T-007 | Stress threat: Most executable AP basket details and actual stock-loan supply are not public. | REQ-004,NFR-001 | Placebo, bootstrap, capacity check |
| T-008 | Reviewer signoff, source license audit, conservative rollback | NFR-001,NFR-002/AC-005,AC-006 | Valid rights and human go/no-go |
## Proposed test IDs (not executed)
1. `test_etf_basket_stockloan_flow_asof`
2. `test_etf_basket_stockloan_flow_baseline`
3. `test_etf_basket_stockloan_flow_negative`
4. `test_etf_basket_stockloan_flow_rights`
**Done means tested engineering evidence, not just Markdown completion.**
