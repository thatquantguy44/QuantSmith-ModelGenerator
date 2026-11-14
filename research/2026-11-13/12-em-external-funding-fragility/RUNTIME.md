# RUNTIME — EM External-Funding Fragility via Currency Mismatch and IIP
**STATUS: proposed, NOT EXECUTABLE.** Any CLI below is a future interface contract.

## Entry point and input schema
`qmg.research.em_external_funding_fragility.cli`. Required JSON/YAML config fields:
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
python -m qmg.research.em_external_funding_fragility.cli validate --config configs/research-example.yaml
python -m qmg.research.em_external_funding_fragility.cli replay --config configs/research-example.yaml --synthetic-only
python -m qmg.research.em_external_funding_fragility.cli evaluate --config configs/research-example.yaml --holdout
```

## Runtime mathematical role
- Model objective: `Fragility_c,t=(FX_credit_c,t - liquid_FX_assets_c,t)/GDP_c,t + λ*short_debt_service_c,t; optimize w for worst-case loss`.
- Variables: c denotes country; all stocks denominated in comparable FX units; FX-credit and external-assets proxies can have incompatible reporting definitions requiring explicit normalization.
- Input contract: IMF IIP, BIS global liquidity quarterly FX credit, OECD macro where available, public reserve series and FX/sovereign returns.
- Cost, timing and capacity: quarterly risk changes after actual statistical release; never refresh historic positions with today's revised values; Use liquid EM FX forwards/ETFs only where available; include carry, forward points, market depth and capital controls.

## Future outputs (not generated)
`run_envelope.json` with source hashes/vintages/versions, `eligible_actions.json`, `baseline_metrics.json`, `candidate_metrics.json`, `confidence_intervals.json`, `claim_ledger.md`, `human_review.md`.

## Failure codes and operational controls
`SOURCE_UNLICENSED`, `FUTURE_INFORMATION`, `MISSING_VINTAGE`, `INVALID_UNIT`, `INFEASIBLE_CONSTRAINT`, `EXECUTION_UNAVAILABLE`, `NOT_IDENTIFIED`.
All errors fail closed with explicit reason; no fallback trading. Monitor source lag and policy drift; rollout and rollback require separate reviewed code/CI evidence.
