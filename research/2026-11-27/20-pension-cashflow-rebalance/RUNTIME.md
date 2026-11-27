# RUNTIME — Global Pension Contribution-Aware Rebalancing with Trading Frictions
**QMG-20261127-20 | B — Domestic/global markets | US, UK, Canada and Netherlands institutional allocation | proposal only**
**Proposed only; modules/commands do not exist.** Runtime contract for qmg.research.pension_cashflow_rebalance: config as_of_utc, source_ids, license_class, grain, decision_cutoff, eligible_universe, limits, cost_model, train/validation/holdout, seed, solver_tolerance. Ingest policy weights, cash contributions/benefits, portfolio NAV, returns and executable costs; only annual OECD releases for long-run calibration; approved plan cashflows known before month-end decisions. Output run_manifest.json, source_ledger.json, baseline_metrics.json, candidate_metrics.json, decision.md and test artifacts with net transaction costs, tracking error, liquidity shortfalls, turnover. Fail closed on LICENSE_BLOCKED, CLOCK_INVALID, INFEASIBLE, MISSING_COST, INSUFFICIENT_HOLDOUT. Example future commands:
```bash
python -m qmg.research.pension_cashflow_rebalance.cli validate --config config.yaml
python -m qmg.research.pension_cashflow_rebalance.cli replay --synthetic --config config.yaml
python -m qmg.research.pension_cashflow_rebalance.cli evaluate --holdout --config config.yaml
```
Set compute budget and pin exact packages after benchmark; no private data in public output.
