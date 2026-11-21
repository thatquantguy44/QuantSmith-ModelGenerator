# TASKS — Public BDC Portfolio Fair-Value Markdown Lead Indicator
**All not started; completion must be evidenced.**
| Task | Description | Maps to | Definition of done |
|---|---|---|---|
| T-001 | Confirm legally feasible decision: Prioritize due diligence or credit hedges where public business development company holdings imply delayed loan fair-value marks. | REQ-001/AC-001 | Independent domain sign-off |
| T-002 | Define BDC filing × portfolio company/sector × disclosure timestamp and synthetic valid/invalid time fixtures | REQ-001,NFR-001 | Immutable schema + missing/late data failures |
| T-003 | Recreate costed benchmark: BDC aggregate NAV discount and published nonaccrual percentage | REQ-002/AC-002 | Deterministic unit tests and cost ledger |
| T-004 | Implement Issuer-level mark-hazard panel with censored holdings and missing-not-at-random controls | REQ-003/AC-003 | Code, pinned config, deterministic seed |
| T-005 | Study Hierarchical Bayesian marked-to-market credit migration model with portfolio network dependence versus first candidate | REQ-003 | Preplanned ablation, no post-hoc switching |
| T-006 | Walk-forward out-of-sample test of Public issuer-level BDC portfolio mark dispersion identifies future credit event/downgrade risk after controlling for BDC leverage and macro credit spread. | REQ-004/AC-004 | Independent holdout results, net-of-cost metrics |
| T-007 | Stress threat: BDC portfolio company identities, valuation methods and distressed sales are not uniformly disclosed; matching bias. | REQ-004,NFR-001 | Placebo, bootstrap, capacity check |
| T-008 | Reviewer signoff, source license audit, conservative rollback | NFR-001,NFR-002/AC-005,AC-006 | Valid rights and human go/no-go |
## Proposed test IDs (not executed)
1. `test_us_bdc_private_credit_marks_asof`
2. `test_us_bdc_private_credit_marks_baseline`
3. `test_us_bdc_private_credit_marks_negative`
4. `test_us_bdc_private_credit_marks_rights`
**Done means tested engineering evidence, not just Markdown completion.**
