# RUNTIME — Marginal Initial-Margin Attribution for Repo Netting Sets
**QMG-20261127-08 | A — Securities finance | US cleared repo / approved global netting sets | proposal only**
**Proposed only; modules/commands do not exist.** Runtime contract for qmg.research.repo_margin_attribution: config as_of_utc, source_ids, license_class, grain, decision_cutoff, eligible_universe, limits, cost_model, train/validation/holdout, seed, solver_tolerance. Ingest trade exposures, margin calculator/version, collateral requirements, legal partitions, realized margin changes; snapshot and calculator version known at allocation; never use future netting trades. Output run_manifest.json, source_ledger.json, baseline_metrics.json, candidate_metrics.json, decision.md and test artifacts with reconciliation error, holdout marginal-cost error, allocation stability, compute time. Fail closed on LICENSE_BLOCKED, CLOCK_INVALID, INFEASIBLE, MISSING_COST, INSUFFICIENT_HOLDOUT. Example future commands:
```bash
python -m qmg.research.repo_margin_attribution.cli validate --config config.yaml
python -m qmg.research.repo_margin_attribution.cli replay --synthetic --config config.yaml
python -m qmg.research.repo_margin_attribution.cli evaluate --holdout --config config.yaml
```
Set compute budget and pin exact packages after benchmark; no private data in public output.
