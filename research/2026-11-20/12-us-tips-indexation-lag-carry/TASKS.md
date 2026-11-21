# TASKS — US TIPS CPI Indexation-Lag Carry and Breakeven Calendar Surface
**All not started; completion must be evidenced.**
| Task | Description | Maps to | Definition of done |
|---|---|---|---|
| T-001 | Confirm legally feasible decision: Select TIPS versus nominal duration-hedged exposure around CPI index-ratio carry windows. | REQ-001/AC-001 | Independent domain sign-off |
| T-002 | Define TIPS CUSIP × CPI/index-ratio effective date × decision timestamp and synthetic valid/invalid time fixtures | REQ-001,NFR-001 | Immutable schema + missing/late data failures |
| T-003 | Recreate costed benchmark: Duration-matched TIPS-minus-nominal bond without CPI-calendar signal | REQ-002/AC-002 | Deterministic unit tests and cost ledger |
| T-004 | Implement Deterministic index-ratio accrual and liquidity-factor attribution | REQ-003/AC-003 | Code, pinned config, deterministic seed |
| T-005 | Study State-space real/nominal curve with stochastic CPI surprise and inflation floor convexity versus first candidate | REQ-003 | Preplanned ablation, no post-hoc switching |
| T-006 | Walk-forward out-of-sample test of A vintage-consistent carry decomposition improves matched-duration real-vs-nominal excess-return hedging net of liquidity/rollover costs. | REQ-004/AC-004 | Independent holdout results, net-of-cost metrics |
| T-007 | Stress threat: Illiquid issue quotations, inflation floor optionality, unrevised CPI data and seasonality overfit. | REQ-004,NFR-001 | Placebo, bootstrap, capacity check |
| T-008 | Reviewer signoff, source license audit, conservative rollback | NFR-001,NFR-002/AC-005,AC-006 | Valid rights and human go/no-go |
## Proposed test IDs (not executed)
1. `test_us_tips_indexation_lag_carry_asof`
2. `test_us_tips_indexation_lag_carry_baseline`
3. `test_us_tips_indexation_lag_carry_negative`
4. `test_us_tips_indexation_lag_carry_rights`
**Done means tested engineering evidence, not just Markdown completion.**
