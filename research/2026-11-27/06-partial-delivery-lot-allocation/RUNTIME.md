# RUNTIME — Partial Securities Delivery Allocation under Minimum Lot Rules
**QMG-20261127-06 | A — Securities finance | US and European securities settlement | proposal only**
**Proposed only; modules/commands do not exist.** Runtime contract for qmg.research.partial_delivery_lot_allocation: config as_of_utc, source_ids, license_class, grain, decision_cutoff, eligible_universe, limits, cost_model, train/validation/holdout, seed, solver_tolerance. Ingest remaining obligations, settled inventory, minimum lot, partial permission, costs, deadlines and acknowledgments; before each cutoff with confirmed deliverable stock; pending receipts excluded. Output run_manifest.json, source_ledger.json, baseline_metrics.json, candidate_metrics.json, decision.md and test artifacts with weighted undelivered shares, net fail fees, message count, missed cutoffs. Fail closed on LICENSE_BLOCKED, CLOCK_INVALID, INFEASIBLE, MISSING_COST, INSUFFICIENT_HOLDOUT. Example future commands:
```bash
python -m qmg.research.partial_delivery_lot_allocation.cli validate --config config.yaml
python -m qmg.research.partial_delivery_lot_allocation.cli replay --synthetic --config config.yaml
python -m qmg.research.partial_delivery_lot_allocation.cli evaluate --holdout --config config.yaml
```
Set compute budget and pin exact packages after benchmark; no private data in public output.
