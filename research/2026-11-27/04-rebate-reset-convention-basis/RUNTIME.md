# RUNTIME — Benchmark Reset Convention Basis in Securities Loan Rebates
**QMG-20261127-04 | A — Securities finance | USD and GBP cash-collateral lending | proposal only**
**Proposed only; modules/commands do not exist.** Runtime contract for qmg.research.rebate_reset_convention_basis: config as_of_utc, source_ids, license_class, grain, decision_cutoff, eligible_universe, limits, cost_model, train/validation/holdout, seed, solver_tolerance. Ingest rate benchmark vintages, executed convention text, spread, calendars, balance and asset accruals; fixings available only after publication; project unknown future rates as scenarios, never realized inputs. Output run_manifest.json, source_ledger.json, baseline_metrics.json, candidate_metrics.json, decision.md and test artifacts with reconciliation USD, residual basis, projected mismatch, fixture accuracy. Fail closed on LICENSE_BLOCKED, CLOCK_INVALID, INFEASIBLE, MISSING_COST, INSUFFICIENT_HOLDOUT. Example future commands:
```bash
python -m qmg.research.rebate_reset_convention_basis.cli validate --config config.yaml
python -m qmg.research.rebate_reset_convention_basis.cli replay --synthetic --config config.yaml
python -m qmg.research.rebate_reset_convention_basis.cli evaluate --holdout --config config.yaml
```
Set compute budget and pin exact packages after benchmark; no private data in public output.
