# TASKS — EU ETS Auction Supply Revision and Carbon Futures Carry
**All not started; completion must be evidenced.**
| Task | Description | Maps to | Definition of done |
|---|---|---|---|
| T-001 | Confirm legally feasible decision: Hedge EUA futures calendar spreads against only announced changes in auction volume and verified-emissions obligations. | REQ-001/AC-001 | Independent domain sign-off |
| T-002 | Define EU ETS auction calendar publication × allowance futures tenor × exchange quote timestamp and synthetic valid/invalid time fixtures | REQ-001,NFR-001 | Immutable schema + missing/late data failures |
| T-003 | Recreate costed benchmark: Calendar-month fixed seasonal allowance spread | REQ-002/AC-002 | Deterministic unit tests and cost ledger |
| T-004 | Implement Event study of auction schedule revisions and futures risk factors | REQ-003/AC-003 | Code, pinned config, deterministic seed |
| T-005 | Study Partial equilibrium allowance banking model with endogenous industrial abatement and policy scenarios versus first candidate | REQ-003 | Preplanned ablation, no post-hoc switching |
| T-006 | Walk-forward out-of-sample test of Public-vintage auction-volume shocks improve calendar-spread/hedge-risk forecasts beyond front-month momentum and seasonal dummies. | REQ-004/AC-004 | Independent holdout results, net-of-cost metrics |
| T-007 | Stress threat: Policy revision expectations may be priced before official publication; futures/Registry coverage not contemporaneous. | REQ-004,NFR-001 | Placebo, bootstrap, capacity check |
| T-008 | Reviewer signoff, source license audit, conservative rollback | NFR-001,NFR-002/AC-005,AC-006 | Valid rights and human go/no-go |
## Proposed test IDs (not executed)
1. `test_eu_ets_auction_carbon_carry_asof`
2. `test_eu_ets_auction_carbon_carry_baseline`
3. `test_eu_ets_auction_carbon_carry_negative`
4. `test_eu_ets_auction_carbon_carry_rights`
**Done means tested engineering evidence, not just Markdown completion.**
