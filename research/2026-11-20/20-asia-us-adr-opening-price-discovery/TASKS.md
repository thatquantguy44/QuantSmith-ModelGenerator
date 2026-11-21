# TASKS — Asia–US Cross-Listed ADR Opening Auction Information Transfer
**All not started; completion must be evidenced.**
| Task | Description | Maps to | Definition of done |
|---|---|---|---|
| T-001 | Confirm legally feasible decision: Choose hedge and execution timing for US ADR versus home-market overnight fair value. | REQ-001/AC-001 | Independent domain sign-off |
| T-002 | Define ADR × home-market session × US opening-auction timestamp and synthetic valid/invalid time fixtures | REQ-001,NFR-001 | Immutable schema + missing/late data failures |
| T-003 | Recreate costed benchmark: Last home close × publicly known ADR conversion ratio × contemporaneous FX spot | REQ-002/AC-002 | Deterministic unit tests and cost ledger |
| T-004 | Implement State-space asynchronous Kalman fair-value update using futures and related peer prices | REQ-003/AC-003 | Code, pinned config, deterministic seed |
| T-005 | Study Continuous-time latent-price discovery with joint jump and optimal execution inventory control versus first candidate | REQ-003 | Preplanned ablation, no post-hoc switching |
| T-006 | Walk-forward out-of-sample test of An asynchronous local-information estimator reduces US ADR opening-price execution error beyond last local close plus FX conversion. | REQ-004/AC-004 | Independent holdout results, net-of-cost metrics |
| T-007 | Stress threat: ADR conversion fees, access restrictions, local holidays and stale home quotes create phantom arbitrage. | REQ-004,NFR-001 | Placebo, bootstrap, capacity check |
| T-008 | Reviewer signoff, source license audit, conservative rollback | NFR-001,NFR-002/AC-005,AC-006 | Valid rights and human go/no-go |
## Proposed test IDs (not executed)
1. `test_asia_us_adr_opening_price_discovery_asof`
2. `test_asia_us_adr_opening_price_discovery_baseline`
3. `test_asia_us_adr_opening_price_discovery_negative`
4. `test_asia_us_adr_opening_price_discovery_rights`
**Done means tested engineering evidence, not just Markdown completion.**
