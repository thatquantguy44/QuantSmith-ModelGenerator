# TASKS — Issuer Customer-Concentration Disclosure to Earnings Options Skew
**All not started; completion must be evidenced.**
| Task | Description | Maps to | Definition of done |
|---|---|---|---|
| T-001 | Confirm legally feasible decision: Hedge customer-loss jump risk in companies with concentrated customers using explicitly costed options structures. | REQ-001/AC-001 | Independent domain sign-off |
| T-002 | Define issuer accepted filing × reported customer share × options quote timestamp and synthetic valid/invalid time fixtures | REQ-001,NFR-001 | Immutable schema + missing/late data failures |
| T-003 | Recreate costed benchmark: Size/leverage/industry/earnings event-only option skew estimator | REQ-002/AC-002 | Deterministic unit tests and cost ledger |
| T-004 | Implement Censored-disclosure panel with inverse observation probability adjustment | REQ-003/AC-003 | Code, pinned config, deterministic seed |
| T-005 | Study Jump-diffusion structural model of concentrated-customer exit hazard versus first candidate | REQ-003 | Preplanned ablation, no post-hoc switching |
| T-006 | Walk-forward out-of-sample test of Point-in-time EDGAR customer concentration disclosures explain forward options downside skew changes beyond leverage, size and event vol. | REQ-004/AC-004 | Independent holdout results, net-of-cost metrics |
| T-007 | Stress threat: Customer concentrations may be anonymized and nonrandomly omitted; options trade data can be illiquid. | REQ-004,NFR-001 | Placebo, bootstrap, capacity check |
| T-008 | Reviewer signoff, source license audit, conservative rollback | NFR-001,NFR-002/AC-005,AC-006 | Valid rights and human go/no-go |
## Proposed test IDs (not executed)
1. `test_customer_concentration_options_skew_asof`
2. `test_customer_concentration_options_skew_baseline`
3. `test_customer_concentration_options_skew_negative`
4. `test_customer_concentration_options_skew_rights`
**Done means tested engineering evidence, not just Markdown completion.**
