# RUNTIME — Asia–US Cross-Listed ADR Opening Auction Information Transfer
**Status:** PROPOSED ONLY. No executable CLI, data store, model or agent exists in this project folder.

## Package path and inputs
`qmg.research.asia_us_adr_opening_price_discovery`
JSON/YAML future config keys:
`run_id, as_of_utc, source_ids, data_license_class, decision_clock, historical_vintages, market_calendar, input_grain, eligibility, cost_model, capital_limit, train_window, holdout_window, random_seed, output_uri`.
Input grain: ADR × home-market session × US opening-auction timestamp. Modeled decision: Choose hedge and execution timing for US ADR versus home-market overnight fair value..

## Hypothetical future CLI, not runnable today
```bash
python -m qmg.research.asia_us_adr_opening_price_discovery.cli validate --config configs/demo.yaml --synthetic
python -m qmg.research.asia_us_adr_opening_price_discovery.cli baseline --config configs/demo.yaml --synthetic
python -m qmg.research.asia_us_adr_opening_price_discovery.cli evaluate --config configs/review.yaml --holdout
```
Expected outputs: `run_manifest.json`, `source_ledger.json`, `metrics.json`, `negative_tests.json`, `review.md`.

## Fail-closed codes
`SOURCE_NOT_LICENSED`, `PIT_LEAKAGE`, `INFEASIBLE_CONSTRAINT`, `UNDEFINED_EXECUTION_COST`, `INSUFFICIENT_HOLDOUT`, `HUMAN_APPROVAL_REQUIRED`.
Record reproducibility seed, hashes, solver tolerance, numerical precision, calendar and max drawdown before any production discussion.
