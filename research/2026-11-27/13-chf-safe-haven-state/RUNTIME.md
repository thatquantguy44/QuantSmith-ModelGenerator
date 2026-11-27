# RUNTIME — Swiss Franc Conditional Safe-Haven Hedge Reliability
**QMG-20261127-13 | B — Domestic/global markets | Switzerland, euro area and global risk portfolios | proposal only**
**Proposed only; modules/commands do not exist.** Runtime contract for qmg.research.chf_safe_haven_state: config as_of_utc, source_ids, license_class, grain, decision_cutoff, eligible_universe, limits, cost_model, train/validation/holdout, seed, solver_tolerance. Ingest CHF exchange rates, policy rates, risk factors, global equity returns, executable FX hedge quotes; daily decisions after all required markets close, execute next quote; no revised intervention data. Output run_manifest.json, source_ledger.json, baseline_metrics.json, candidate_metrics.json, decision.md and test artifacts with expected shortfall, carry, hedge hit rate, turnover. Fail closed on LICENSE_BLOCKED, CLOCK_INVALID, INFEASIBLE, MISSING_COST, INSUFFICIENT_HOLDOUT. Example future commands:
```bash
python -m qmg.research.chf_safe_haven_state.cli validate --config config.yaml
python -m qmg.research.chf_safe_haven_state.cli replay --synthetic --config config.yaml
python -m qmg.research.chf_safe_haven_state.cli evaluate --holdout --config config.yaml
```
Set compute budget and pin exact packages after benchmark; no private data in public output.
