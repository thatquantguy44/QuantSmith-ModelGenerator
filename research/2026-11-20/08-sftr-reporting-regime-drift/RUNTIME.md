# RUNTIME — SFTR Reporting Regime Drift and Public-Private Divergence Detector
**Status:** PROPOSED ONLY. No executable CLI, data store, model or agent exists in this project folder.

## Package path and inputs
`qmg.research.sftr_reporting_regime_drift`
JSON/YAML future config keys:
`run_id, as_of_utc, source_ids, data_license_class, decision_clock, historical_vintages, market_calendar, input_grain, eligibility, cost_model, capital_limit, train_window, holdout_window, random_seed, output_uri`.
Input grain: SFTR public aggregate series × jurisdiction × report vintage. Modeled decision: Detect structural reporting-quality breaks before using reported SFTR aggregates as market exposure signals..

## Hypothetical future CLI, not runnable today
```bash
python -m qmg.research.sftr_reporting_regime_drift.cli validate --config configs/demo.yaml --synthetic
python -m qmg.research.sftr_reporting_regime_drift.cli baseline --config configs/demo.yaml --synthetic
python -m qmg.research.sftr_reporting_regime_drift.cli evaluate --config configs/review.yaml --holdout
```
Expected outputs: `run_manifest.json`, `source_ledger.json`, `metrics.json`, `negative_tests.json`, `review.md`.

## Fail-closed codes
`SOURCE_NOT_LICENSED`, `PIT_LEAKAGE`, `INFEASIBLE_CONSTRAINT`, `UNDEFINED_EXECUTION_COST`, `INSUFFICIENT_HOLDOUT`, `HUMAN_APPROVAL_REQUIRED`.
Record reproducibility seed, hashes, solver tolerance, numerical precision, calendar and max drawdown before any production discussion.
