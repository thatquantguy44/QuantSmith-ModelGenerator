# RUNTIME — Brazil Reservoir Water Value and Utility Earnings Risk
**QMG-20261127-17 | B — Domestic/global markets | Brazil hydroelectric generation and utility equities | proposal only**
**Proposed only; modules/commands do not exist.** Runtime contract for qmg.research.brazil_reservoir_water_value: config as_of_utc, source_ids, license_class, grain, decision_cutoff, eligible_universe, limits, cost_model, train/validation/holdout, seed, solver_tolerance. Ingest stored energy, inflow, generation, load, thermal costs, transmission constraints, issuer contract exposures; only archived public release versions; ONS data may revise; forecast issuance known before decision. Output run_manifest.json, source_ledger.json, baseline_metrics.json, candidate_metrics.json, decision.md and test artifacts with marginal cost MAE, reliability, earnings scenario error, feasible dispatch. Fail closed on LICENSE_BLOCKED, CLOCK_INVALID, INFEASIBLE, MISSING_COST, INSUFFICIENT_HOLDOUT. Example future commands:
```bash
python -m qmg.research.brazil_reservoir_water_value.cli validate --config config.yaml
python -m qmg.research.brazil_reservoir_water_value.cli replay --synthetic --config config.yaml
python -m qmg.research.brazil_reservoir_water_value.cli evaluate --holdout --config config.yaml
```
Set compute budget and pin exact packages after benchmark; no private data in public output.
