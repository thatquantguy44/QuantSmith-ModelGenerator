# RUNTIME — Securities-Lending Circular Flow Surveillance via Temporal Graphs
**Status:** PROPOSED ONLY. No executable CLI, data store, model or agent exists in this project folder.

## Package path and inputs
`qmg.research.seclending_circular_flow_surveillance`
JSON/YAML future config keys:
`run_id, as_of_utc, source_ids, data_license_class, decision_clock, historical_vintages, market_calendar, input_grain, eligibility, cost_model, capital_limit, train_window, holdout_window, random_seed, output_uri`.
Input grain: synthetic securities loan transfer edge × security × event timestamp. Modeled decision: Escalate suspicious short-lived circular borrow/return patterns for compliance review without inferring wrongdoing from volume alone..

## Hypothetical future CLI, not runnable today
```bash
python -m qmg.research.seclending_circular_flow_surveillance.cli validate --config configs/demo.yaml --synthetic
python -m qmg.research.seclending_circular_flow_surveillance.cli baseline --config configs/demo.yaml --synthetic
python -m qmg.research.seclending_circular_flow_surveillance.cli evaluate --config configs/review.yaml --holdout
```
Expected outputs: `run_manifest.json`, `source_ledger.json`, `metrics.json`, `negative_tests.json`, `review.md`.

## Fail-closed codes
`SOURCE_NOT_LICENSED`, `PIT_LEAKAGE`, `INFEASIBLE_CONSTRAINT`, `UNDEFINED_EXECUTION_COST`, `INSUFFICIENT_HOLDOUT`, `HUMAN_APPROVAL_REQUIRED`.
Record reproducibility seed, hashes, solver tolerance, numerical precision, calendar and max drawdown before any production discussion.
