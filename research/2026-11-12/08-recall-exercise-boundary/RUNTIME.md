# RUNTIME — Loan Recall Early-Exercise Boundary
**Proposed executable contract. Nothing here has been implemented.**
## Entry module
`qmg.research.recall_exercise_boundary.cli`
## Config keys
`run_id, as_of_utc, source_ids, source_license_class, decision_clock, cost_model, risk_limits, eligibility, train_start, train_end, holdout_start, holdout_end, random_seed, output_dir`.
## Example future invocations (illustrative only)
```bash
python -m qmg.research.recall_exercise_boundary.cli validate --config config.yaml
python -m qmg.research.recall_exercise_boundary.cli replay --synthetic --config config.yaml
python -m qmg.research.recall_exercise_boundary.cli evaluate --holdout --config config.yaml
```
## Expected outputs (not created)
`run_manifest.json`, `source_ledger.json`, `baseline_metrics.json`, `candidate_metrics.json`, `review.md`.
Fail closed with `SOURCE_UNLICENSED`, `FUTURE_LEAKAGE`, `INFEASIBLE`, `MISSING_COST`, `INSUFFICIENT_HOLDOUT`. Human signoff before connecting live data.
