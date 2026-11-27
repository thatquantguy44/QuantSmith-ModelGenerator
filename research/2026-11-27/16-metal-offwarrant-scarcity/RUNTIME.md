# RUNTIME — Exchange Metals Off-Warrant Inventory and Calendar-Spread Scarcity
**QMG-20261127-16 | B — Domestic/global markets | London Metal Exchange global base metals | proposal only**
**Proposed only; modules/commands do not exist.** Runtime contract for qmg.research.metal_offwarrant_scarcity: config as_of_utc, source_ids, license_class, grain, decision_cutoff, eligible_universe, limits, cost_model, train/validation/holdout, seed, solver_tolerance. Ingest off/on-warrant inventories, cancellations, warehouse movements, futures settlements, financing/storage costs; free data only after actual T+3 or current verified delay; paid T+1 separately; execute next quote. Output run_manifest.json, source_ledger.json, baseline_metrics.json, candidate_metrics.json, decision.md and test artifacts with MAE, curve sign accuracy, net spread P&L, capacity. Fail closed on LICENSE_BLOCKED, CLOCK_INVALID, INFEASIBLE, MISSING_COST, INSUFFICIENT_HOLDOUT. Example future commands:
```bash
python -m qmg.research.metal_offwarrant_scarcity.cli validate --config config.yaml
python -m qmg.research.metal_offwarrant_scarcity.cli replay --synthetic --config config.yaml
python -m qmg.research.metal_offwarrant_scarcity.cli evaluate --holdout --config config.yaml
```
Set compute budget and pin exact packages after benchmark; no private data in public output.
