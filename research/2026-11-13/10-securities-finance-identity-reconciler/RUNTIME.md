# RUNTIME — Cross-Book Securities Finance Identity Reconciliation Graph
**STATUS: proposed, NOT EXECUTABLE.** Any CLI below is a future interface contract.

## Entry point and input schema
`qmg.research.securities_finance_identity_reconciler.cli`. Required JSON/YAML config fields:
```yaml
run_id: "synthetic-example-only"
as_of_utc: "YYYY-MM-DDTHH:MM:SSZ"
license_class: "public|licensed|restricted"
decision_time_utc: "YYYY-MM-DDTHH:MM:SSZ"
source_vintages: []
market_calendar: "approved-market-calendar"
train_start: "YYYY-MM-DD"
train_end: "YYYY-MM-DD"
holdout_start: "YYYY-MM-DD"
holdout_end: "YYYY-MM-DD"
random_seed: 123
risk_limits: {}
cost_model: {}
synthetic_only: true
```

## Future commands — do not run until code exists
```bash
python -m qmg.research.securities_finance_identity_reconciler.cli validate --config configs/research-example.yaml
python -m qmg.research.securities_finance_identity_reconciler.cli replay --config configs/research-example.yaml --synthetic-only
python -m qmg.research.securities_finance_identity_reconciler.cli evaluate --config configs/research-example.yaml --holdout
```

## Runtime mathematical role
- Model objective: `min_M Σ_(i,j) c_ij*M_ij + λ*unmatched(M); M_ij∈{0,1}, one-to-one constraints and incompatible identifier rules`.
- Variables: M_ij selects a candidate match between external and canonical records; c_ij is audited mismatch cost with hard ID prohibitions.
- Input contract: Synthetic records containing lifecycle events, ISIN/CUSIP, product type, settlement date, amount, counterparty alias and amendment chain.
- Cost, timing and capacity: real-time/overnight reconciliation; no future correction can be applied retroactively to a prior risk snapshot; No market capacity required; scalability measured in records/day and audit/log cost, not claimed P&L.

## Future outputs (not generated)
`run_envelope.json` with source hashes/vintages/versions, `eligible_actions.json`, `baseline_metrics.json`, `candidate_metrics.json`, `confidence_intervals.json`, `claim_ledger.md`, `human_review.md`.

## Failure codes and operational controls
`SOURCE_UNLICENSED`, `FUTURE_INFORMATION`, `MISSING_VINTAGE`, `INVALID_UNIT`, `INFEASIBLE_CONSTRAINT`, `EXECUTION_UNAVAILABLE`, `NOT_IDENTIFIED`.
All errors fail closed with explicit reason; no fallback trading. Monitor source lag and policy drift; rollout and rollback require separate reviewed code/CI evidence.
