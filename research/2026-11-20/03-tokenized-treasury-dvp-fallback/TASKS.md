# TASKS — Tokenized Treasury Collateral DvP Finality and Fallback Stress
**All not started; completion must be evidenced.**
| Task | Description | Maps to | Definition of done |
|---|---|---|---|
| T-001 | Confirm legally feasible decision: Select permitted collateral settlement pathway with provable delivery-versus-payment, finality and fail-safe fallback. | REQ-001/AC-001 | Independent domain sign-off |
| T-002 | Define collateral lot × settlement leg × wallet/ledger state × timestamp and synthetic valid/invalid time fixtures | REQ-001,NFR-001 | Immutable schema + missing/late data failures |
| T-003 | Recreate costed benchmark: Conventional permitted book-entry DvP with settlement cutoff | REQ-002/AC-002 | Deterministic unit tests and cost ledger |
| T-004 | Implement Timed Petri net state-machine model of mint/transfer/burn and escrow/finality rules | REQ-003/AC-003 | Code, pinned config, deterministic seed |
| T-005 | Study Formal model checking of cross-system DvP atomicity with stochastic disruption transitions versus first candidate | REQ-003 | Preplanned ablation, no post-hoc switching |
| T-006 | Walk-forward out-of-sample test of A permissioned DvP route with explicit finality state and contingency transfer reduces stress settlement lockup against conventional-only or optimistic atomic-claim baselines. | REQ-004/AC-004 | Independent holdout results, net-of-cost metrics |
| T-007 | Stress threat: Token entitlements must not be treated as interchangeable with every conventional collateral/clearing agreement. | REQ-004,NFR-001 | Placebo, bootstrap, capacity check |
| T-008 | Reviewer signoff, source license audit, conservative rollback | NFR-001,NFR-002/AC-005,AC-006 | Valid rights and human go/no-go |
## Proposed test IDs (not executed)
1. `test_tokenized_treasury_dvp_fallback_asof`
2. `test_tokenized_treasury_dvp_fallback_baseline`
3. `test_tokenized_treasury_dvp_fallback_negative`
4. `test_tokenized_treasury_dvp_fallback_rights`
**Done means tested engineering evidence, not just Markdown completion.**
