# RUNTIME — Securities-Lending Fee Observability & Selection-Bias Corrector
**STATUS: proposed, NOT EXECUTABLE.** Any CLI below is a future interface contract.

## Entry point and input schema
`qmg.research.lending_fee_selection_debiasing.cli`. Required JSON/YAML config fields:
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
python -m qmg.research.lending_fee_selection_debiasing.cli validate --config configs/research-example.yaml
python -m qmg.research.lending_fee_selection_debiasing.cli replay --config configs/research-example.yaml --synthetic-only
python -m qmg.research.lending_fee_selection_debiasing.cli evaluate --config configs/research-example.yaml --holdout
```

## Runtime mathematical role
- Model objective: `mu_hat = Σ_i w_i*y_i/Σ_i w_i; w_i=1/P(observed_i|X_i); report sensitivity to unidentified selection`.
- Variables: y_i is observed fee; X_i observable security/liquidity/context; propensity weights are estimated from an externally validated sample frame.
- Input contract: Contributed executed fee samples; public security volume/short-interest proxies; locate response metadata; source coverage and revisions.
- Cost, timing and capacity: benchmark at next published cutoff; never use end-of-day contributions before receipt; Primarily an internal benchmark/data product; no automatic quoting when source coverage or liquidity is inadequate.

## Future outputs (not generated)
`run_envelope.json` with source hashes/vintages/versions, `eligible_actions.json`, `baseline_metrics.json`, `candidate_metrics.json`, `confidence_intervals.json`, `claim_ledger.md`, `human_review.md`.

## Failure codes and operational controls
`SOURCE_UNLICENSED`, `FUTURE_INFORMATION`, `MISSING_VINTAGE`, `INVALID_UNIT`, `INFEASIBLE_CONSTRAINT`, `EXECUTION_UNAVAILABLE`, `NOT_IDENTIFIED`.
All errors fail closed with explicit reason; no fallback trading. Monitor source lag and policy drift; rollout and rollback require separate reviewed code/CI evidence.
