# RUNTIME — US Small-Cap ATM Equity Issuance Dilution Hazard
**QMG-20261127-11 | B — Domestic/global markets | US small-cap equities | proposal only**
**Proposed only; modules/commands do not exist.** Runtime contract for qmg.research.atm_issuance_dilution_hazard: config as_of_utc, source_ids, license_class, grain, decision_cutoff, eligible_universe, limits, cost_model, train/validation/holdout, seed, solver_tolerance. Ingest 424B prospectuses, 8-K/10-Q share counts, cash burn, issuance disclosures, delisting-adjusted returns; first dissemination of each accession, next tradable session; quarter issuance outcomes after filings. Output run_manifest.json, source_ledger.json, baseline_metrics.json, candidate_metrics.json, decision.md and test artifacts with Brier, dilution MAE, event return attribution, false-alert rate. Fail closed on LICENSE_BLOCKED, CLOCK_INVALID, INFEASIBLE, MISSING_COST, INSUFFICIENT_HOLDOUT. Example future commands:
```bash
python -m qmg.research.atm_issuance_dilution_hazard.cli validate --config config.yaml
python -m qmg.research.atm_issuance_dilution_hazard.cli replay --synthetic --config config.yaml
python -m qmg.research.atm_issuance_dilution_hazard.cli evaluate --holdout --config config.yaml
```
Set compute budget and pin exact packages after benchmark; no private data in public output.
