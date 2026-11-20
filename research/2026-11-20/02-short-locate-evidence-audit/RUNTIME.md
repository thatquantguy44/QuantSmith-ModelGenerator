# RUNTIME — Reg SHO Locate Evidence and Borrow-Capacity Audit Engine
**Status:** PROPOSED ONLY. No executable CLI, data store, model or agent exists in this project folder.

## Package path and inputs
`qmg.research.short_locate_evidence_audit`
JSON/YAML future config keys:
`run_id, as_of_utc, source_ids, data_license_class, decision_clock, historical_vintages, market_calendar, input_grain, eligibility, cost_model, capital_limit, train_window, holdout_window, random_seed, output_uri`.
Input grain: short-sale request × account × security × source × event timestamp. Modeled decision: Block or escalate a short-sale request if contemporaneous legally qualifying locate evidence or remaining documented quantity is insufficient..

## Hypothetical future CLI, not runnable today
```bash
python -m qmg.research.short_locate_evidence_audit.cli validate --config configs/demo.yaml --synthetic
python -m qmg.research.short_locate_evidence_audit.cli baseline --config configs/demo.yaml --synthetic
python -m qmg.research.short_locate_evidence_audit.cli evaluate --config configs/review.yaml --holdout
```
Expected outputs: `run_manifest.json`, `source_ledger.json`, `metrics.json`, `negative_tests.json`, `review.md`.

## Fail-closed codes
`SOURCE_NOT_LICENSED`, `PIT_LEAKAGE`, `INFEASIBLE_CONSTRAINT`, `UNDEFINED_EXECUTION_COST`, `INSUFFICIENT_HOLDOUT`, `HUMAN_APPROVAL_REQUIRED`.
Record reproducibility seed, hashes, solver tolerance, numerical precision, calendar and max drawdown before any production discussion.
