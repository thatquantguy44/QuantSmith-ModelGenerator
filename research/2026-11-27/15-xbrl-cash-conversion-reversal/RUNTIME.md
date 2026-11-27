# RUNTIME — Accrual Cash-Conversion Reversal with XBRL Restatement Lineage
**QMG-20261127-15 | B — Domestic/global markets | US and foreign SEC reporting equities | proposal only**
**Proposed only; modules/commands do not exist.** Runtime contract for qmg.research.xbrl_cash_conversion_reversal: config as_of_utc, source_ids, license_class, grain, decision_cutoff, eligible_universe, limits, cost_model, train/validation/holdout, seed, solver_tolerance. Ingest cash flow, net income, assets, receivables, inventory, restatements, taxonomy mappings and delisting records; first filing acceptance/dissemination, with later amended accession separate; decisions next session. Output run_manifest.json, source_ledger.json, baseline_metrics.json, candidate_metrics.json, decision.md and test artifacts with cash-flow MAE, tag mapping precision, forecast IC, coverage. Fail closed on LICENSE_BLOCKED, CLOCK_INVALID, INFEASIBLE, MISSING_COST, INSUFFICIENT_HOLDOUT. Example future commands:
```bash
python -m qmg.research.xbrl_cash_conversion_reversal.cli validate --config config.yaml
python -m qmg.research.xbrl_cash_conversion_reversal.cli replay --synthetic --config config.yaml
python -m qmg.research.xbrl_cash_conversion_reversal.cli evaluate --holdout --config config.yaml
```
Set compute budget and pin exact packages after benchmark; no private data in public output.
