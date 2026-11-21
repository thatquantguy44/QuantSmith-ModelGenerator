# RUNTIME — Wheat Export Inspection Revisions to Global Basis and Calendar Spreads
**Status:** PROPOSED ONLY. No executable CLI, data store, model or agent exists in this project folder.

## Package path and inputs
`qmg.research.global_wheat_export_inspection_basis`
JSON/YAML future config keys:
`run_id, as_of_utc, source_ids, data_license_class, decision_clock, historical_vintages, market_calendar, input_grain, eligibility, cost_model, capital_limit, train_window, holdout_window, random_seed, output_uri`.
Input grain: weekly USDA inspection release × grain class × destination × exchange quote timestamp. Modeled decision: Hedge wheat calendar spreads around official export inspection versus world balance-sheet information releases..

## Hypothetical future CLI, not runnable today
```bash
python -m qmg.research.global_wheat_export_inspection_basis.cli validate --config configs/demo.yaml --synthetic
python -m qmg.research.global_wheat_export_inspection_basis.cli baseline --config configs/demo.yaml --synthetic
python -m qmg.research.global_wheat_export_inspection_basis.cli evaluate --config configs/review.yaml --holdout
```
Expected outputs: `run_manifest.json`, `source_ledger.json`, `metrics.json`, `negative_tests.json`, `review.md`.

## Fail-closed codes
`SOURCE_NOT_LICENSED`, `PIT_LEAKAGE`, `INFEASIBLE_CONSTRAINT`, `UNDEFINED_EXECUTION_COST`, `INSUFFICIENT_HOLDOUT`, `HUMAN_APPROVAL_REQUIRED`.
Record reproducibility seed, hashes, solver tolerance, numerical precision, calendar and max drawdown before any production discussion.
