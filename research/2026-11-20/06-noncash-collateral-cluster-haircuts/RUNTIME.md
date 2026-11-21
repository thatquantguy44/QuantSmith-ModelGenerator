# RUNTIME — Noncash Collateral Correlation-Cluster Haircut Controller
**Status:** PROPOSED ONLY. No executable CLI, data store, model or agent exists in this project folder.

## Package path and inputs
`qmg.research.noncash_collateral_cluster_haircuts`
JSON/YAML future config keys:
`run_id, as_of_utc, source_ids, data_license_class, decision_clock, historical_vintages, market_calendar, input_grain, eligibility, cost_model, capital_limit, train_window, holdout_window, random_seed, output_uri`.
Input grain: collateral security × issuer cluster × loan exposure × as-of time. Modeled decision: Recommend minimum defensive haircuts for a collateral basket based on joint concentration and liquidation correlation..

## Hypothetical future CLI, not runnable today
```bash
python -m qmg.research.noncash_collateral_cluster_haircuts.cli validate --config configs/demo.yaml --synthetic
python -m qmg.research.noncash_collateral_cluster_haircuts.cli baseline --config configs/demo.yaml --synthetic
python -m qmg.research.noncash_collateral_cluster_haircuts.cli evaluate --config configs/review.yaml --holdout
```
Expected outputs: `run_manifest.json`, `source_ledger.json`, `metrics.json`, `negative_tests.json`, `review.md`.

## Fail-closed codes
`SOURCE_NOT_LICENSED`, `PIT_LEAKAGE`, `INFEASIBLE_CONSTRAINT`, `UNDEFINED_EXECUTION_COST`, `INSUFFICIENT_HOLDOUT`, `HUMAN_APPROVAL_REQUIRED`.
Record reproducibility seed, hashes, solver tolerance, numerical precision, calendar and max drawdown before any production discussion.
