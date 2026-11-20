# RUNTIME — EU ETS Auction Supply Revision and Carbon Futures Carry
**Status:** PROPOSED ONLY. No executable CLI, data store, model or agent exists in this project folder.

## Package path and inputs
`qmg.research.eu_ets_auction_carbon_carry`
JSON/YAML future config keys:
`run_id, as_of_utc, source_ids, data_license_class, decision_clock, historical_vintages, market_calendar, input_grain, eligibility, cost_model, capital_limit, train_window, holdout_window, random_seed, output_uri`.
Input grain: EU ETS auction calendar publication × allowance futures tenor × exchange quote timestamp. Modeled decision: Hedge EUA futures calendar spreads against only announced changes in auction volume and verified-emissions obligations..

## Hypothetical future CLI, not runnable today
```bash
python -m qmg.research.eu_ets_auction_carbon_carry.cli validate --config configs/demo.yaml --synthetic
python -m qmg.research.eu_ets_auction_carbon_carry.cli baseline --config configs/demo.yaml --synthetic
python -m qmg.research.eu_ets_auction_carbon_carry.cli evaluate --config configs/review.yaml --holdout
```
Expected outputs: `run_manifest.json`, `source_ledger.json`, `metrics.json`, `negative_tests.json`, `review.md`.

## Fail-closed codes
`SOURCE_NOT_LICENSED`, `PIT_LEAKAGE`, `INFEASIBLE_CONSTRAINT`, `UNDEFINED_EXECUTION_COST`, `INSUFFICIENT_HOLDOUT`, `HUMAN_APPROVAL_REQUIRED`.
Record reproducibility seed, hashes, solver tolerance, numerical precision, calendar and max drawdown before any production discussion.
