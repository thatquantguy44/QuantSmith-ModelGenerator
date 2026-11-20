# RUNTIME — Global Shipping Connectivity Re-Routing to Inflation and Equity Margins
**Status:** PROPOSED ONLY. No executable CLI, data store, model or agent exists in this project folder.

## Package path and inputs
`qmg.research.global_port_connectivity_inflation`
JSON/YAML future config keys:
`run_id, as_of_utc, source_ids, data_license_class, decision_clock, historical_vintages, market_calendar, input_grain, eligibility, cost_model, capital_limit, train_window, holdout_window, random_seed, output_uri`.
Input grain: country/port route × monthly index release × subsequent inflation/earnings outcome. Modeled decision: Size logistics/inflation hedges when public route connectivity and port-service centrality shift..

## Hypothetical future CLI, not runnable today
```bash
python -m qmg.research.global_port_connectivity_inflation.cli validate --config configs/demo.yaml --synthetic
python -m qmg.research.global_port_connectivity_inflation.cli baseline --config configs/demo.yaml --synthetic
python -m qmg.research.global_port_connectivity_inflation.cli evaluate --config configs/review.yaml --holdout
```
Expected outputs: `run_manifest.json`, `source_ledger.json`, `metrics.json`, `negative_tests.json`, `review.md`.

## Fail-closed codes
`SOURCE_NOT_LICENSED`, `PIT_LEAKAGE`, `INFEASIBLE_CONSTRAINT`, `UNDEFINED_EXECUTION_COST`, `INSUFFICIENT_HOLDOUT`, `HUMAN_APPROVAL_REQUIRED`.
Record reproducibility seed, hashes, solver tolerance, numerical precision, calendar and max drawdown before any production discussion.
