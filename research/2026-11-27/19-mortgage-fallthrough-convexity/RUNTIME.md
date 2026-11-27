# RUNTIME — US Mortgage Origination Fall-Through and Rate-Lock Convexity
**QMG-20261127-19 | B — Domestic/global markets | US residential mortgage origination and rates | proposal only**
**Proposed only; modules/commands do not exist.** Runtime contract for qmg.research.mortgage_fallthrough_convexity: config as_of_utc, source_ids, license_class, grain, decision_cutoff, eligible_universe, limits, cost_model, train/validation/holdout, seed, solver_tolerance. Ingest loan outcomes, rates, application attributes, actual lock time, lock rate/expiry, hedge prices; public HMDA only after annual release; private locks timestamped before hedge; no demographic targeting. Output run_manifest.json, source_ledger.json, baseline_metrics.json, candidate_metrics.json, decision.md and test artifacts with hedge error, pull-through calibration, bias, cost and residual duration. Fail closed on LICENSE_BLOCKED, CLOCK_INVALID, INFEASIBLE, MISSING_COST, INSUFFICIENT_HOLDOUT. Example future commands:
```bash
python -m qmg.research.mortgage_fallthrough_convexity.cli validate --config config.yaml
python -m qmg.research.mortgage_fallthrough_convexity.cli replay --synthetic --config config.yaml
python -m qmg.research.mortgage_fallthrough_convexity.cli evaluate --holdout --config config.yaml
```
Set compute budget and pin exact packages after benchmark; no private data in public output.
