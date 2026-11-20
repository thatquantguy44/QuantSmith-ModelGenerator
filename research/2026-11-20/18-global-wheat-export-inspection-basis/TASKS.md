# TASKS — Wheat Export Inspection Revisions to Global Basis and Calendar Spreads
**All not started; completion must be evidenced.**
| Task | Description | Maps to | Definition of done |
|---|---|---|---|
| T-001 | Confirm legally feasible decision: Hedge wheat calendar spreads around official export inspection versus world balance-sheet information releases. | REQ-001/AC-001 | Independent domain sign-off |
| T-002 | Define weekly USDA inspection release × grain class × destination × exchange quote timestamp and synthetic valid/invalid time fixtures | REQ-001,NFR-001 | Immutable schema + missing/late data failures |
| T-003 | Recreate costed benchmark: Monthly seasonal wheat spread regression using last known WASDE | REQ-002/AC-002 | Deterministic unit tests and cost ledger |
| T-004 | Implement Mixed-frequency distributed-lag export surprise model | REQ-003/AC-003 | Code, pinned config, deterministic seed |
| T-005 | Study Structural Bayesian crop-flow network with regional stock constraints and censoring versus first candidate | REQ-003 | Preplanned ablation, no post-hoc switching |
| T-006 | Walk-forward out-of-sample test of Vintage-corrected inspection surprises anticipate regional wheat basis and nearby-deferred spread movements beyond seasonality and WASDE. | REQ-004/AC-004 | Independent holdout results, net-of-cost metrics |
| T-007 | Stress threat: Weekly inspections differ from actual export commitments; Black Sea supply and policy announcements may dominate. | REQ-004,NFR-001 | Placebo, bootstrap, capacity check |
| T-008 | Reviewer signoff, source license audit, conservative rollback | NFR-001,NFR-002/AC-005,AC-006 | Valid rights and human go/no-go |
## Proposed test IDs (not executed)
1. `test_global_wheat_export_inspection_basis_asof`
2. `test_global_wheat_export_inspection_basis_baseline`
3. `test_global_wheat_export_inspection_basis_negative`
4. `test_global_wheat_export_inspection_basis_rights`
**Done means tested engineering evidence, not just Markdown completion.**
