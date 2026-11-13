# RUNTIME — Cash versus Noncash Loan-Collateral Economic Frontier
**STATUS: proposed, NOT EXECUTABLE.** Any CLI below is a future interface contract.

## Entry point and input schema
`qmg.research.cash_noncash_lending_collateral_frontier.cli`. Required JSON/YAML config fields:
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
python -m qmg.research.cash_noncash_lending_collateral_frontier.cli validate --config configs/research-example.yaml
python -m qmg.research.cash_noncash_lending_collateral_frontier.cli replay --config configs/research-example.yaml --synthetic-only
python -m qmg.research.cash_noncash_lending_collateral_frontier.cli evaluate --config configs/research-example.yaml --holdout
```

## Runtime mathematical role
- Model objective: `max_(j∈allowed) [borrow_fee_j + permissible_reinvestment_yield_j - rebate_j - liquidity_cost_j - expected_loss_j - capital_j]`.
- Variables: j denotes a feasible collateral convention; values must use common horizon and comparable currency-adjusted cash flows.
- Input contract: Cash and noncash terms, rebate schedules, reinvestment constraints, asset eligibility, mark-to-market, haircuts and legal restrictions.
- Cost, timing and capacity: quote acceptance before loan opening with known collateral terms, not end-of-day realized earnings; Constrained by approved collateral classes, reinvestment capacity, borrower credit and liquidity.

## Future outputs (not generated)
`run_envelope.json` with source hashes/vintages/versions, `eligible_actions.json`, `baseline_metrics.json`, `candidate_metrics.json`, `confidence_intervals.json`, `claim_ledger.md`, `human_review.md`.

## Failure codes and operational controls
`SOURCE_UNLICENSED`, `FUTURE_INFORMATION`, `MISSING_VINTAGE`, `INVALID_UNIT`, `INFEASIBLE_CONSTRAINT`, `EXECUTION_UNAVAILABLE`, `NOT_IDENTIFIED`.
All errors fail closed with explicit reason; no fallback trading. Monitor source lag and policy drift; rollout and rollback require separate reviewed code/CI evidence.
