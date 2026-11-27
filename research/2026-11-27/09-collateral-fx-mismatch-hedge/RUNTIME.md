# RUNTIME — Collateral FX Mismatch Hedge under Margin Revaluation
**QMG-20261127-09 | A — Securities finance | USD/EUR/GBP securities finance | proposal only**
**Proposed only; modules/commands do not exist.** Runtime contract for qmg.research.collateral_fx_mismatch_hedge: config as_of_utc, source_ids, license_class, grain, decision_cutoff, eligible_universe, limits, cost_model, train/validation/holdout, seed, solver_tolerance. Ingest contract currency, collateral value, FX quotes, hedge instruments, margin frequency, hedge liquidity and constraints; only FX quotes/eligibility known before margin and hedge cutoff; hedge at next executable quote. Output run_manifest.json, source_ledger.json, baseline_metrics.json, candidate_metrics.json, decision.md and test artifacts with margin call ES, hedge slippage, capital/FX residual, hard constraints. Fail closed on LICENSE_BLOCKED, CLOCK_INVALID, INFEASIBLE, MISSING_COST, INSUFFICIENT_HOLDOUT. Example future commands:
```bash
python -m qmg.research.collateral_fx_mismatch_hedge.cli validate --config config.yaml
python -m qmg.research.collateral_fx_mismatch_hedge.cli replay --synthetic --config config.yaml
python -m qmg.research.collateral_fx_mismatch_hedge.cli evaluate --holdout --config config.yaml
```
Set compute budget and pin exact packages after benchmark; no private data in public output.
