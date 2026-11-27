# RUNTIME — Countercyclical Repo Haircut Adjustment with Hysteresis
**QMG-20261127-02 | A — Securities finance | US/EU non-cleared secured funding | proposal only**
**Proposed only; modules/commands do not exist.** Runtime contract for qmg.research.haircut_hysteresis_policy: config as_of_utc, source_ids, license_class, grain, decision_cutoff, eligible_universe, limits, cost_model, train/validation/holdout, seed, solver_tolerance. Ingest haircut vintages, eligible collateral marks, stress indicators, margin calls and realized liquidation outcomes; previously published volatility/rates, signed terms before risk decision. Output run_manifest.json, source_ledger.json, baseline_metrics.json, candidate_metrics.json, decision.md and test artifacts with p99 incremental margin call, expected shortfall of closeout, floor breaches. Fail closed on LICENSE_BLOCKED, CLOCK_INVALID, INFEASIBLE, MISSING_COST, INSUFFICIENT_HOLDOUT. Example future commands:
```bash
python -m qmg.research.haircut_hysteresis_policy.cli validate --config config.yaml
python -m qmg.research.haircut_hysteresis_policy.cli replay --synthetic --config config.yaml
python -m qmg.research.haircut_hysteresis_policy.cli evaluate --holdout --config config.yaml
```
Set compute budget and pin exact packages after benchmark; no private data in public output.
