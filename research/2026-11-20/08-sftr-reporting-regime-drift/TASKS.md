# TASKS — SFTR Reporting Regime Drift and Public-Private Divergence Detector
**All not started; completion must be evidenced.**
| Task | Description | Maps to | Definition of done |
|---|---|---|---|
| T-001 | Confirm legally feasible decision: Detect structural reporting-quality breaks before using reported SFTR aggregates as market exposure signals. | REQ-001/AC-001 | Independent domain sign-off |
| T-002 | Define SFTR public aggregate series × jurisdiction × report vintage and synthetic valid/invalid time fixtures | REQ-001,NFR-001 | Immutable schema + missing/late data failures |
| T-003 | Recreate costed benchmark: Fixed ±3-sigma z-score alert on each series | REQ-002/AC-002 | Deterministic unit tests and cost ledger |
| T-004 | Implement Robust multivariate Bayesian online change-point detection | REQ-003/AC-003 | Code, pinned config, deterministic seed |
| T-005 | Study Hierarchical regime/missingness change-point models with document version embeddings as covariates versus first candidate | REQ-003 | Preplanned ablation, no post-hoc switching |
| T-006 | Walk-forward out-of-sample test of Joint change-point tests on volumes, missingness and reported collateral taxonomy identify synthetic or historical reporting breaks more reliably than absolute-value outlier rules. | REQ-004/AC-004 | Independent holdout results, net-of-cost metrics |
| T-007 | Stress threat: Only public aggregate data may be available, making root-cause verification incomplete. | REQ-004,NFR-001 | Placebo, bootstrap, capacity check |
| T-008 | Reviewer signoff, source license audit, conservative rollback | NFR-001,NFR-002/AC-005,AC-006 | Valid rights and human go/no-go |
## Proposed test IDs (not executed)
1. `test_sftr_reporting_regime_drift_asof`
2. `test_sftr_reporting_regime_drift_baseline`
3. `test_sftr_reporting_regime_drift_negative`
4. `test_sftr_reporting_regime_drift_rights`
**Done means tested engineering evidence, not just Markdown completion.**
