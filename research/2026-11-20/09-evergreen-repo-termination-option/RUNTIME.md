# RUNTIME — Evergreen Repo Early-Termination Optionality Risk Budget
**Status:** PROPOSED ONLY. No executable CLI, data store, model or agent exists in this project folder.

## Package path and inputs
`qmg.research.evergreen_repo_termination_option`
JSON/YAML future config keys:
`run_id, as_of_utc, source_ids, data_license_class, decision_clock, historical_vintages, market_calendar, input_grain, eligibility, cost_model, capital_limit, train_window, holdout_window, random_seed, output_uri`.
Input grain: contract × notice period × funding day × interest-rate state. Modeled decision: Set rate/tenor risk charges for unilateral termination and extension rights in open repo or evergreen funding..

## Hypothetical future CLI, not runnable today
```bash
python -m qmg.research.evergreen_repo_termination_option.cli validate --config configs/demo.yaml --synthetic
python -m qmg.research.evergreen_repo_termination_option.cli baseline --config configs/demo.yaml --synthetic
python -m qmg.research.evergreen_repo_termination_option.cli evaluate --config configs/review.yaml --holdout
```
Expected outputs: `run_manifest.json`, `source_ledger.json`, `metrics.json`, `negative_tests.json`, `review.md`.

## Fail-closed codes
`SOURCE_NOT_LICENSED`, `PIT_LEAKAGE`, `INFEASIBLE_CONSTRAINT`, `UNDEFINED_EXECUTION_COST`, `INSUFFICIENT_HOLDOUT`, `HUMAN_APPROVAL_REQUIRED`.
Record reproducibility seed, hashes, solver tolerance, numerical precision, calendar and max drawdown before any production discussion.
