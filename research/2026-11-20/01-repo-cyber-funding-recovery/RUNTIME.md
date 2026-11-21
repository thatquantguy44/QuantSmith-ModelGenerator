# RUNTIME — Cyber-Outage Contingent Repo Funding Recovery Routes
**Status:** PROPOSED ONLY. No executable CLI, data store, model or agent exists in this project folder.

## Package path and inputs
`qmg.research.repo_cyber_funding_recovery`
JSON/YAML future config keys:
`run_id, as_of_utc, source_ids, data_license_class, decision_clock, historical_vintages, market_calendar, input_grain, eligibility, cost_model, capital_limit, train_window, holdout_window, random_seed, output_uri`.
Input grain: route × lender class × hourly outage scenario. Modeled decision: Pre-approve alternate cash-lender/clearing routes and reserve a minimum contingency liquidity buffer for an exogenous operational outage..

## Hypothetical future CLI, not runnable today
```bash
python -m qmg.research.repo_cyber_funding_recovery.cli validate --config configs/demo.yaml --synthetic
python -m qmg.research.repo_cyber_funding_recovery.cli baseline --config configs/demo.yaml --synthetic
python -m qmg.research.repo_cyber_funding_recovery.cli evaluate --config configs/review.yaml --holdout
```
Expected outputs: `run_manifest.json`, `source_ledger.json`, `metrics.json`, `negative_tests.json`, `review.md`.

## Fail-closed codes
`SOURCE_NOT_LICENSED`, `PIT_LEAKAGE`, `INFEASIBLE_CONSTRAINT`, `UNDEFINED_EXECUTION_COST`, `INSUFFICIENT_HOLDOUT`, `HUMAN_APPROVAL_REQUIRED`.
Record reproducibility seed, hashes, solver tolerance, numerical precision, calendar and max drawdown before any production discussion.
