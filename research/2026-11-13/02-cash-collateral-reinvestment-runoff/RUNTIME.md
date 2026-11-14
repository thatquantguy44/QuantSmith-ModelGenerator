# RUNTIME — Cash-Collateral Reinvestment Liquidity Run-Off Controller
**STATUS: proposed, NOT EXECUTABLE.** Any CLI below is a future interface contract.

## Entry point and input schema
`qmg.research.cash_collateral_reinvestment_runoff.cli`. Required JSON/YAML config fields:
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
python -m qmg.research.cash_collateral_reinvestment_runoff.cli validate --config configs/research-example.yaml
python -m qmg.research.cash_collateral_reinvestment_runoff.cli replay --config configs/research-example.yaml --synthetic-only
python -m qmg.research.cash_collateral_reinvestment_runoff.cli evaluate --config configs/research-example.yaml --holdout
```

## Runtime mathematical role
- Model objective: `min_w E[funding_cost(w)+liquidity_shortfall_penalty(w)] + λ CVaR_99(shortfall(w)); Σ_k w_k=1; WAM/WAL/eligibility and liquidity floors hold`.
- Variables: w_k is share in maturity/liquidity bucket k; CVaR_99 is 99% expected shortfall on repayment funding deficits, not investment P&L.
- Input contract: Loan termination flows; collateral principal; reinvestment settlement and maturity ladders; redemption windows; eligible funds; short-term yields; stress scenarios.
- Cost, timing and capacity: end-of-day reinvestment decision with availability of prior published cash flow and eligible settlement windows; Capital is constrained by contractual permissible instruments, concentration, tenor limits and financing market depth.

## Future outputs (not generated)
`run_envelope.json` with source hashes/vintages/versions, `eligible_actions.json`, `baseline_metrics.json`, `candidate_metrics.json`, `confidence_intervals.json`, `claim_ledger.md`, `human_review.md`.

## Failure codes and operational controls
`SOURCE_UNLICENSED`, `FUTURE_INFORMATION`, `MISSING_VINTAGE`, `INVALID_UNIT`, `INFEASIBLE_CONSTRAINT`, `EXECUTION_UNAVAILABLE`, `NOT_IDENTIFIED`.
All errors fail closed with explicit reason; no fallback trading. Monitor source lag and policy drift; rollout and rollback require separate reviewed code/CI evidence.
