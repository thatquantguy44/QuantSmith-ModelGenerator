# RUNTIME — Repo RFQ Disclosure-Width versus Execution Competition
**QMG-20261127-07 | A — Securities finance | US and UK institutional repo | proposal only**
**Proposed only; modules/commands do not exist.** Runtime contract for qmg.research.repo_rfq_disclosure_width: config as_of_utc, source_ids, license_class, grain, decision_cutoff, eligible_universe, limits, cost_model, train/validation/holdout, seed, solver_tolerance. Ingest RFQ timestamps, eligible recipients, executable responses, trade cost, approved randomization assignment and later price drift; assign before outreach; only historical availability and quote freshness; observe outcomes later. Output run_manifest.json, source_ledger.json, baseline_metrics.json, candidate_metrics.json, decision.md and test artifacts with all-in cost, fill probability, post-RFQ drift, coverage and latency. Fail closed on LICENSE_BLOCKED, CLOCK_INVALID, INFEASIBLE, MISSING_COST, INSUFFICIENT_HOLDOUT. Example future commands:
```bash
python -m qmg.research.repo_rfq_disclosure_width.cli validate --config config.yaml
python -m qmg.research.repo_rfq_disclosure_width.cli replay --synthetic --config config.yaml
python -m qmg.research.repo_rfq_disclosure_width.cli evaluate --holdout --config config.yaml
```
Set compute budget and pin exact packages after benchmark; no private data in public output.
