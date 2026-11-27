# RUNTIME — Repo Maturity Mismatch Early-Warning via Survival Cash Ladders
**QMG-20261127-10 | A — Securities finance | US and European matched-book secured funding | proposal only**
**Proposed only; modules/commands do not exist.** Runtime contract for qmg.research.repo_maturity_gap_survival: config as_of_utc, source_ids, license_class, grain, decision_cutoff, eligible_universe, limits, cost_model, train/validation/holdout, seed, solver_tolerance. Ingest maturity dates, historical renewals/nonrenewals, counterparty segment, rates, confirmed inflows and cutoff; decision before maturity; only renewals confirmed by snapshot; outcomes as labels. Output run_manifest.json, source_ledger.json, baseline_metrics.json, candidate_metrics.json, decision.md and test artifacts with Brier score, cash-gap quantile coverage, warning lead time, reserve cost. Fail closed on LICENSE_BLOCKED, CLOCK_INVALID, INFEASIBLE, MISSING_COST, INSUFFICIENT_HOLDOUT. Example future commands:
```bash
python -m qmg.research.repo_maturity_gap_survival.cli validate --config config.yaml
python -m qmg.research.repo_maturity_gap_survival.cli replay --synthetic --config config.yaml
python -m qmg.research.repo_maturity_gap_survival.cli evaluate --holdout --config config.yaml
```
Set compute budget and pin exact packages after benchmark; no private data in public output.
