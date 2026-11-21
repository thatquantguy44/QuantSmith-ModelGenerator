# RUNTIME — Japan FX Intervention Impact and Option-Skew Persistence
**Status:** PROPOSED ONLY. No executable CLI, data store, model or agent exists in this project folder.

## Package path and inputs
`qmg.research.japan_fx_intervention_persistence`
JSON/YAML future config keys:
`run_id, as_of_utc, source_ids, data_license_class, decision_clock, historical_vintages, market_calendar, input_grain, eligibility, cost_model, capital_limit, train_window, holdout_window, random_seed, output_uri`.
Input grain: intervention disclosure event × FX option tenor × quote timestamp. Modeled decision: Determine when to reduce/hedge yen exposure following **publicly observed** intervention or subsequent official disclosure..

## Hypothetical future CLI, not runnable today
```bash
python -m qmg.research.japan_fx_intervention_persistence.cli validate --config configs/demo.yaml --synthetic
python -m qmg.research.japan_fx_intervention_persistence.cli baseline --config configs/demo.yaml --synthetic
python -m qmg.research.japan_fx_intervention_persistence.cli evaluate --config configs/review.yaml --holdout
```
Expected outputs: `run_manifest.json`, `source_ledger.json`, `metrics.json`, `negative_tests.json`, `review.md`.

## Fail-closed codes
`SOURCE_NOT_LICENSED`, `PIT_LEAKAGE`, `INFEASIBLE_CONSTRAINT`, `UNDEFINED_EXECUTION_COST`, `INSUFFICIENT_HOLDOUT`, `HUMAN_APPROVAL_REQUIRED`.
Record reproducibility seed, hashes, solver tolerance, numerical precision, calendar and max drawdown before any production discussion.
