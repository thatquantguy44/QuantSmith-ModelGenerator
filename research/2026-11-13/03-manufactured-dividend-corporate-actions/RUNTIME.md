# RUNTIME — Manufactured-Dividend and Corporate-Action Loan Economics
**STATUS: proposed, NOT EXECUTABLE.** Any CLI below is a future interface contract.

## Entry point and input schema
`qmg.research.manufactured_dividend_corporate_actions.cli`. Required JSON/YAML config fields:
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
python -m qmg.research.manufactured_dividend_corporate_actions.cli validate --config configs/research-example.yaml
python -m qmg.research.manufactured_dividend_corporate_actions.cli replay --config configs/research-example.yaml --synthetic-only
python -m qmg.research.manufactured_dividend_corporate_actions.cli evaluate --config configs/research-example.yaml --holdout
```

## Runtime mathematical role
- Model objective: `max_(a in eligible_actions) [fee(a)-manufactured_payment_adjustment(a)-corporate_action_cost(a)-recall_cost(a)-tax_adjustment(a)]`.
- Variables: a is a legally permitted loan lifecycle action; each component is booked at the owner-specific event date and in consistent after-tax units.
- Input contract: Ex/record/pay dates; loan life; fee accrual; event elections; dividend amounts; owner tax flags and permitted return/recall rules.
- Cost, timing and capacity: event decisions before ex-date cutoff, using only announced corporate actions and approved tax interpretations then available; Only owner-permitted loans and action windows; supply cannot be fabricated by the optimizer.

## Future outputs (not generated)
`run_envelope.json` with source hashes/vintages/versions, `eligible_actions.json`, `baseline_metrics.json`, `candidate_metrics.json`, `confidence_intervals.json`, `claim_ledger.md`, `human_review.md`.

## Failure codes and operational controls
`SOURCE_UNLICENSED`, `FUTURE_INFORMATION`, `MISSING_VINTAGE`, `INVALID_UNIT`, `INFEASIBLE_CONSTRAINT`, `EXECUTION_UNAVAILABLE`, `NOT_IDENTIFIED`.
All errors fail closed with explicit reason; no fallback trading. Monitor source lag and policy drift; rollout and rollback require separate reviewed code/CI evidence.
