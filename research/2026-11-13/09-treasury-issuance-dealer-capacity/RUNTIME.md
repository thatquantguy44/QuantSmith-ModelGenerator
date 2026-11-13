# RUNTIME — Treasury Issuance-to-Dealer Intermediation Capacity Map
**STATUS: proposed, NOT EXECUTABLE.** Any CLI below is a future interface contract.

## Entry point and input schema
`qmg.research.treasury_issuance_dealer_capacity.cli`. Required JSON/YAML config fields:
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
python -m qmg.research.treasury_issuance_dealer_capacity.cli validate --config configs/research-example.yaml
python -m qmg.research.treasury_issuance_dealer_capacity.cli replay --config configs/research-example.yaml --synthetic-only
python -m qmg.research.treasury_issuance_dealer_capacity.cli evaluate --config configs/research-example.yaml --holdout
```

## Runtime mathematical role
- Model objective: `C_t=Δissuance_t - β*Δdealer_financed_positions_t; p_(t+h)=sigmoid(α+γ*C_(available≤t)+δ*vol_t)`.
- Variables: C_t is an issuance-absorption mismatch proxy, not observed dealer capital; p is stress probability, h is pre-set future horizon.
- Input contract: Treasury auction issuance and settlement schedule; weekly primary dealer net positions/financing; OFR repo aggregates; public Treasury yield changes.
- Cost, timing and capacity: weekly close after primary dealer publication; never treat reported prior-week positions as contemporaneous; Public signal is a risk overlay; tradability needs actual Treasury order book, bid/ask, duration and repo access.

## Future outputs (not generated)
`run_envelope.json` with source hashes/vintages/versions, `eligible_actions.json`, `baseline_metrics.json`, `candidate_metrics.json`, `confidence_intervals.json`, `claim_ledger.md`, `human_review.md`.

## Failure codes and operational controls
`SOURCE_UNLICENSED`, `FUTURE_INFORMATION`, `MISSING_VINTAGE`, `INVALID_UNIT`, `INFEASIBLE_CONSTRAINT`, `EXECUTION_UNAVAILABLE`, `NOT_IDENTIFIED`.
All errors fail closed with explicit reason; no fallback trading. Monitor source lag and policy drift; rollout and rollback require separate reviewed code/CI evidence.
