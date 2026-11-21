# TASKS — Canadian Mortgage Renewal Cohorts to Bank Credit-Risk Dispersion
**All not started; completion must be evidenced.**
| Task | Description | Maps to | Definition of done |
|---|---|---|---|
| T-001 | Confirm legally feasible decision: Hedge Canadian bank credit/equity risk using public maturity-cohort mortgage renewal exposure rather than broad unemployment alone. | REQ-001/AC-001 | Independent domain sign-off |
| T-002 | Define Canadian mortgage cohort × monthly public release × bank quarterly filing and synthetic valid/invalid time fixtures | REQ-001,NFR-001 | Immutable schema + missing/late data failures |
| T-003 | Recreate costed benchmark: Bank loss sensitivity to national unemployment and policy rate alone | REQ-002/AC-002 | Deterministic unit tests and cost ledger |
| T-004 | Implement Vintage-cohort mortgage reset microsimulation from public aggregates | REQ-003/AC-003 | Code, pinned config, deterministic seed |
| T-005 | Study Hierarchical hazard model linking repricing, prepayment and issuer loan-level exposures versus first candidate | REQ-003 | Preplanned ablation, no post-hoc switching |
| T-006 | Walk-forward out-of-sample test of Estimated vintage-conditioned payment shock predicts cross-bank loan loss and valuation dispersion beyond level rates and employment controls. | REQ-004/AC-004 | Independent holdout results, net-of-cost metrics |
| T-007 | Stress threat: Public aggregate cohorts do not identify each bank's borrower vintage distribution or underwriting quality. | REQ-004,NFR-001 | Placebo, bootstrap, capacity check |
| T-008 | Reviewer signoff, source license audit, conservative rollback | NFR-001,NFR-002/AC-005,AC-006 | Valid rights and human go/no-go |
## Proposed test IDs (not executed)
1. `test_canadian_mortgage_renewal_bank_risk_asof`
2. `test_canadian_mortgage_renewal_bank_risk_baseline`
3. `test_canadian_mortgage_renewal_bank_risk_negative`
4. `test_canadian_mortgage_renewal_bank_risk_rights`
**Done means tested engineering evidence, not just Markdown completion.**
