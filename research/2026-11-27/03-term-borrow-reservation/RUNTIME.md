# RUNTIME — Forward Borrow Capacity Reservation for Committed Term Loans
**QMG-20261127-03 | A — Securities finance | US and European equity stock loan | proposal only**
**Proposed only; modules/commands do not exist.** Runtime contract for qmg.research.term_borrow_reservation: config as_of_utc, source_ids, license_class, grain, decision_cutoff, eligible_universe, limits, cost_model, train/validation/holdout, seed, solver_tolerance. Ingest signed term commitments, available shares, draw schedules, spot fees, cancellations, replacement cost; at commitment acceptance or daily reserve review; only confirmed mandates and availability. Output run_manifest.json, source_ledger.json, baseline_metrics.json, candidate_metrics.json, decision.md and test artifacts with shortage shares, realized reservation cost, service coverage, revenue. Fail closed on LICENSE_BLOCKED, CLOCK_INVALID, INFEASIBLE, MISSING_COST, INSUFFICIENT_HOLDOUT. Example future commands:
```bash
python -m qmg.research.term_borrow_reservation.cli validate --config config.yaml
python -m qmg.research.term_borrow_reservation.cli replay --synthetic --config config.yaml
python -m qmg.research.term_borrow_reservation.cli evaluate --holdout --config config.yaml
```
Set compute budget and pin exact packages after benchmark; no private data in public output.
