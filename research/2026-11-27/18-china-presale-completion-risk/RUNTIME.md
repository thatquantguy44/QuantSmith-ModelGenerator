# RUNTIME — China Developer Presale Cash-Conversion and Completion Risk
**QMG-20261127-18 | B — Domestic/global markets | China property developers and Asian credit | proposal only**
**Proposed only; modules/commands do not exist.** Runtime contract for qmg.research.china_presale_completion_risk: config as_of_utc, source_ids, license_class, grain, decision_cutoff, eligible_universe, limits, cost_model, train/validation/holdout, seed, solver_tolerance. Ingest sales floor area, deposits/advance receipts, completed/started floor area, issuer cash and debt, escrow restrictions; first NBS report and issuer filing dissemination, convert cumulative series only using same vintage. Output run_manifest.json, source_ledger.json, baseline_metrics.json, candidate_metrics.json, decision.md and test artifacts with distress Brier, calibration, completion error, uncertainty width. Fail closed on LICENSE_BLOCKED, CLOCK_INVALID, INFEASIBLE, MISSING_COST, INSUFFICIENT_HOLDOUT. Example future commands:
```bash
python -m qmg.research.china_presale_completion_risk.cli validate --config config.yaml
python -m qmg.research.china_presale_completion_risk.cli replay --synthetic --config config.yaml
python -m qmg.research.china_presale_completion_risk.cli evaluate --holdout --config config.yaml
```
Set compute budget and pin exact packages after benchmark; no private data in public output.
