# RUNTIME — Mexico Nearshoring Realization versus Industrial Equity Expectations
**QMG-20261127-12 | B — Domestic/global markets | Mexico, US–Mexico industrial corridor | proposal only**
**Proposed only; modules/commands do not exist.** Runtime contract for qmg.research.mexico_nearshoring_realization: config as_of_utc, source_ids, license_class, grain, decision_cutoff, eligible_universe, limits, cost_model, train/validation/holdout, seed, solver_tolerance. Ingest IMMEX staffing/hours, issuer geography, earnings, FX, exports, corporate announcements; first INEGI monthly release and financial report timestamps, region weights frozen before prediction. Output run_manifest.json, source_ledger.json, baseline_metrics.json, candidate_metrics.json, decision.md and test artifacts with MAE, revision sensitivity, sector-neutral forecast IC. Fail closed on LICENSE_BLOCKED, CLOCK_INVALID, INFEASIBLE, MISSING_COST, INSUFFICIENT_HOLDOUT. Example future commands:
```bash
python -m qmg.research.mexico_nearshoring_realization.cli validate --config config.yaml
python -m qmg.research.mexico_nearshoring_realization.cli replay --synthetic --config config.yaml
python -m qmg.research.mexico_nearshoring_realization.cli evaluate --holdout --config config.yaml
```
Set compute budget and pin exact packages after benchmark; no private data in public output.
