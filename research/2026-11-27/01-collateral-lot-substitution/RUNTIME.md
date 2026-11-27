# RUNTIME — Collateral Substitution with Discrete Lot Opportunity Costs
**QMG-20261127-01 | A — Securities finance | US Treasury and European sovereign repo | proposal only**
**Proposed only; modules/commands do not exist.** Runtime contract for qmg.research.collateral_lot_substitution: config as_of_utc, source_ids, license_class, grain, decision_cutoff, eligible_universe, limits, cost_model, train/validation/holdout, seed, solver_tolerance. Ingest lot size, live eligibility, haircut, encumbrance, transfer fees, cutoffs, available inventory and replacement opportunity cost; pre-substitution snapshot; confirm replacement settlement before release; no end-day inventory. Output run_manifest.json, source_ledger.json, baseline_metrics.json, candidate_metrics.json, decision.md and test artifacts with net USD carry/transfer cost, excess collateral, breach count, solve time. Fail closed on LICENSE_BLOCKED, CLOCK_INVALID, INFEASIBLE, MISSING_COST, INSUFFICIENT_HOLDOUT. Example future commands:
```bash
python -m qmg.research.collateral_lot_substitution.cli validate --config config.yaml
python -m qmg.research.collateral_lot_substitution.cli replay --synthetic --config config.yaml
python -m qmg.research.collateral_lot_substitution.cli evaluate --holdout --config config.yaml
```
Set compute budget and pin exact packages after benchmark; no private data in public output.
