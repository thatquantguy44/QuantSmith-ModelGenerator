# RUNTIME — Short Interest versus Securities Loan Utilization State Decomposition
**QMG-20261127-05 | A — Securities finance | US exchange-listed equities | proposal only**
**Proposed only; modules/commands do not exist.** Runtime contract for qmg.research.short_interest_utilization_state: config as_of_utc, source_ids, license_class, grain, decision_cutoff, eligible_universe, limits, cost_model, train/validation/holdout, seed, solver_tolerance. Ingest reported SI, lender availability/utilization, corporate actions, lendable supply and fees; ingest FINRA publication after 4:40 p.m. ET or later actual receipt; trade next eligible session. Output run_manifest.json, source_ledger.json, baseline_metrics.json, candidate_metrics.json, decision.md and test artifacts with MAE, calibration, supply/demand label precision on verified events. Fail closed on LICENSE_BLOCKED, CLOCK_INVALID, INFEASIBLE, MISSING_COST, INSUFFICIENT_HOLDOUT. Example future commands:
```bash
python -m qmg.research.short_interest_utilization_state.cli validate --config config.yaml
python -m qmg.research.short_interest_utilization_state.cli replay --synthetic --config config.yaml
python -m qmg.research.short_interest_utilization_state.cli evaluate --holdout --config config.yaml
```
Set compute budget and pin exact packages after benchmark; no private data in public output.
