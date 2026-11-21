# RUNTIME — ETF Creation/Redemption Basket Shock to Stock-Loan Supply
**Status:** PROPOSED ONLY. No executable CLI, data store, model or agent exists in this project folder.

## Package path and inputs
`qmg.research.etf_basket_stockloan_flow`
JSON/YAML future config keys:
`run_id, as_of_utc, source_ids, data_license_class, decision_clock, historical_vintages, market_calendar, input_grain, eligibility, cost_model, capital_limit, train_window, holdout_window, random_seed, output_uri`.
Input grain: ETF × constituent × creation/redemption day × publication time. Modeled decision: Reserve lendable constituent supply ahead of known or forecasted ETF in-kind redemption/creation windows..

## Hypothetical future CLI, not runnable today
```bash
python -m qmg.research.etf_basket_stockloan_flow.cli validate --config configs/demo.yaml --synthetic
python -m qmg.research.etf_basket_stockloan_flow.cli baseline --config configs/demo.yaml --synthetic
python -m qmg.research.etf_basket_stockloan_flow.cli evaluate --config configs/review.yaml --holdout
```
Expected outputs: `run_manifest.json`, `source_ledger.json`, `metrics.json`, `negative_tests.json`, `review.md`.

## Fail-closed codes
`SOURCE_NOT_LICENSED`, `PIT_LEAKAGE`, `INFEASIBLE_CONSTRAINT`, `UNDEFINED_EXECUTION_COST`, `INSUFFICIENT_HOLDOUT`, `HUMAN_APPROVAL_REQUIRED`.
Record reproducibility seed, hashes, solver tolerance, numerical precision, calendar and max drawdown before any production discussion.
