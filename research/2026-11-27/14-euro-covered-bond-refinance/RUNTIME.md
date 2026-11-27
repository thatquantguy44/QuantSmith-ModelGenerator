# RUNTIME — Euro Bank Covered versus Unsecured Refinancing Maturity Wall
**QMG-20261127-14 | B — Domestic/global markets | Euro area bank credit | proposal only**
**Proposed only; modules/commands do not exist.** Runtime contract for qmg.research.euro_covered_bond_refinance: config as_of_utc, source_ids, license_class, grain, decision_cutoff, eligible_universe, limits, cost_model, train/validation/holdout, seed, solver_tolerance. Ingest covered/unsecured maturities, encumbrance, bank filings, issuance prices, curves, rating history; filing dissemination before monthly decision; issue prices after actual issuance as outcomes. Output run_manifest.json, source_ledger.json, baseline_metrics.json, candidate_metrics.json, decision.md and test artifacts with spread MAE, gap error, coverage, class-adjusted residual. Fail closed on LICENSE_BLOCKED, CLOCK_INVALID, INFEASIBLE, MISSING_COST, INSUFFICIENT_HOLDOUT. Example future commands:
```bash
python -m qmg.research.euro_covered_bond_refinance.cli validate --config config.yaml
python -m qmg.research.euro_covered_bond_refinance.cli replay --synthetic --config config.yaml
python -m qmg.research.euro_covered_bond_refinance.cli evaluate --holdout --config config.yaml
```
Set compute budget and pin exact packages after benchmark; no private data in public output.
