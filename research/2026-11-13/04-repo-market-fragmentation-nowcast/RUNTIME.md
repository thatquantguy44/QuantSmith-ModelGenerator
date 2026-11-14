# RUNTIME — Cleared Versus Tri-Party Repo Fragmentation Nowcast
**STATUS: proposed, NOT EXECUTABLE.** Any CLI below is a future interface contract.

## Entry point and input schema
`qmg.research.repo_market_fragmentation_nowcast.cli`. Required JSON/YAML config fields:
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
python -m qmg.research.repo_market_fragmentation_nowcast.cli validate --config configs/research-example.yaml
python -m qmg.research.repo_market_fragmentation_nowcast.cli replay --config configs/research-example.yaml --synthetic-only
python -m qmg.research.repo_market_fragmentation_nowcast.cli evaluate --config configs/research-example.yaml --holdout
```

## Runtime mathematical role
- Model objective: `F_t=Σ_v ω_v (r_v,t-r_ref,t)^2 + η*HHI(volume_v,t); predict P(stress_(t+1)|F_<=t, publication_lags)`.
- Variables: v indexes funding venue/tenor/collateral categories; weights ω_v normalize liquidity; η calibrates volume concentration penalty.
- Input contract: OFR cleared and tri-party rate-volume series; collateral categories; SOFR; weekly dealer aggregate financing; release metadata.
- Cost, timing and capacity: risk update only after OFR release; cleared repo T+1 and tri-party T+2 availability; never use same-day unpublished values; An alert/risk-overlay product first; any later trade signal faces venue access, funding tenor and prices.

## Future outputs (not generated)
`run_envelope.json` with source hashes/vintages/versions, `eligible_actions.json`, `baseline_metrics.json`, `candidate_metrics.json`, `confidence_intervals.json`, `claim_ledger.md`, `human_review.md`.

## Failure codes and operational controls
`SOURCE_UNLICENSED`, `FUTURE_INFORMATION`, `MISSING_VINTAGE`, `INVALID_UNIT`, `INFEASIBLE_CONSTRAINT`, `EXECUTION_UNAVAILABLE`, `NOT_IDENTIFIED`.
All errors fail closed with explicit reason; no fallback trading. Monitor source lag and policy drift; rollout and rollback require separate reviewed code/CI evidence.
