# RUNTIME — Canadian Mortgage Renewal Cohorts to Bank Credit-Risk Dispersion
**Status:** PROPOSED ONLY. No executable CLI, data store, model or agent exists in this project folder.

## Package path and inputs
`qmg.research.canadian_mortgage_renewal_bank_risk`
JSON/YAML future config keys:
`run_id, as_of_utc, source_ids, data_license_class, decision_clock, historical_vintages, market_calendar, input_grain, eligibility, cost_model, capital_limit, train_window, holdout_window, random_seed, output_uri`.
Input grain: Canadian mortgage cohort × monthly public release × bank quarterly filing. Modeled decision: Hedge Canadian bank credit/equity risk using public maturity-cohort mortgage renewal exposure rather than broad unemployment alone..

## Hypothetical future CLI, not runnable today
```bash
python -m qmg.research.canadian_mortgage_renewal_bank_risk.cli validate --config configs/demo.yaml --synthetic
python -m qmg.research.canadian_mortgage_renewal_bank_risk.cli baseline --config configs/demo.yaml --synthetic
python -m qmg.research.canadian_mortgage_renewal_bank_risk.cli evaluate --config configs/review.yaml --holdout
```
Expected outputs: `run_manifest.json`, `source_ledger.json`, `metrics.json`, `negative_tests.json`, `review.md`.

## Fail-closed codes
`SOURCE_NOT_LICENSED`, `PIT_LEAKAGE`, `INFEASIBLE_CONSTRAINT`, `UNDEFINED_EXECUTION_COST`, `INSUFFICIENT_HOLDOUT`, `HUMAN_APPROVAL_REQUIRED`.
Record reproducibility seed, hashes, solver tolerance, numerical precision, calendar and max drawdown before any production discussion.
