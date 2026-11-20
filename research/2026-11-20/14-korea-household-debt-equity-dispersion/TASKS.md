# TASKS — Korean Household Debt-Service Shock to Bank–Consumer Equity Spread
**All not started; completion must be evidenced.**
| Task | Description | Maps to | Definition of done |
|---|---|---|---|
| T-001 | Confirm legally feasible decision: Hedge relative exposure of Korean bank and consumer equities across household debt-service regime changes. | REQ-001/AC-001 | Independent domain sign-off |
| T-002 | Define quarterly DSR release × issuer × accounting period × price timestamp and synthetic valid/invalid time fixtures | REQ-001,NFR-001 | Immutable schema + missing/late data failures |
| T-003 | Recreate costed benchmark: Equal-beta long banks short consumer discretionary with lagged policy-rate signal | REQ-002/AC-002 | Deterministic unit tests and cost ledger |
| T-004 | Implement Panel local projections with shrinkage and sector time fixed effects | REQ-003/AC-003 | Code, pinned config, deterministic seed |
| T-005 | Study Dynamic heterogeneous household credit impulse response with instrumented policy-rate shocks versus first candidate | REQ-003 | Preplanned ablation, no post-hoc switching |
| T-006 | Walk-forward out-of-sample test of Lag-corrected Korean household DSR changes identify subsequent bank-versus-consumer earnings dispersion beyond policy rates/market beta. | REQ-004/AC-004 | Independent holdout results, net-of-cost metrics |
| T-007 | Stress threat: Endogenous rate policy and sector composition cause confounding; public issuer histories need delisting continuity. | REQ-004,NFR-001 | Placebo, bootstrap, capacity check |
| T-008 | Reviewer signoff, source license audit, conservative rollback | NFR-001,NFR-002/AC-005,AC-006 | Valid rights and human go/no-go |
## Proposed test IDs (not executed)
1. `test_korea_household_debt_equity_dispersion_asof`
2. `test_korea_household_debt_equity_dispersion_baseline`
3. `test_korea_household_debt_equity_dispersion_negative`
4. `test_korea_household_debt_equity_dispersion_rights`
**Done means tested engineering evidence, not just Markdown completion.**
