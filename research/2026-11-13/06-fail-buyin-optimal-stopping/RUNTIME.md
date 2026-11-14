# RUNTIME — Settlement-Fail Buy-In versus Wait Optimal Stopping
**STATUS: proposed, NOT EXECUTABLE.** Any CLI below is a future interface contract.

## Entry point and input schema
`qmg.research.fail_buyin_optimal_stopping.cli`. Required JSON/YAML config fields:
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
python -m qmg.research.fail_buyin_optimal_stopping.cli validate --config configs/research-example.yaml
python -m qmg.research.fail_buyin_optimal_stopping.cli replay --config configs/research-example.yaml --synthetic-only
python -m qmg.research.fail_buyin_optimal_stopping.cli evaluate --config configs/research-example.yaml --holdout
```

## Runtime mathematical role
- Model objective: `V_t(s)=min{cover_cost_t(s), reroute_cost_t(s), fail_penalty_t(s)+E[V_(t+1)(s')|s]}`.
- Variables: s contains security, counterparty, days failed, available cover liquidity and contractual remedy state.
- Input contract: Public dealer failure aggregates for calibration; synthetic failure life histories; approved buy-in quotes, fails charges and legal remedies.
- Cost, timing and capacity: business-day cure decisions only after confirmed fail and remedy eligibility; Limited by available deliverable security and realistic executable cover bids.

## Future outputs (not generated)
`run_envelope.json` with source hashes/vintages/versions, `eligible_actions.json`, `baseline_metrics.json`, `candidate_metrics.json`, `confidence_intervals.json`, `claim_ledger.md`, `human_review.md`.

## Failure codes and operational controls
`SOURCE_UNLICENSED`, `FUTURE_INFORMATION`, `MISSING_VINTAGE`, `INVALID_UNIT`, `INFEASIBLE_CONSTRAINT`, `EXECUTION_UNAVAILABLE`, `NOT_IDENTIFIED`.
All errors fail closed with explicit reason; no fallback trading. Monitor source lag and policy drift; rollout and rollback require separate reviewed code/CI evidence.
