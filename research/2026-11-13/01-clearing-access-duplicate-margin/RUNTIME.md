# RUNTIME — Treasury Clearing Access-Path & Duplicate-Margin Optimizer
**STATUS: proposed, NOT EXECUTABLE.** Any CLI below is a future interface contract.

## Entry point and input schema
`qmg.research.clearing_access_duplicate_margin.cli`. Required JSON/YAML config fields:
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
python -m qmg.research.clearing_access_duplicate_margin.cli validate --config configs/research-example.yaml
python -m qmg.research.clearing_access_duplicate_margin.cli replay --config configs/research-example.yaml --synthetic-only
python -m qmg.research.clearing_access_duplicate_margin.cli evaluate --config configs/research-example.yaml --holdout
```

## Runtime mathematical role
- Model objective: `min_(x_p) Σ_p x_p*(rate_p*notional*T + fee_p + margin_carry_p + default_fund_p + cclf_liquidity_p) - verified_netting_benefit(x); Σ_p x_p=1; x_p=0 for ineligible paths`.
- Variables: x_p is fraction routed through path p; T is year-fraction tenor; margin, default fund, CCLF and netting effects use validated path-specific rules rather than assumed offsets.
- Input contract: Eligible trade templates; path availability; historical quote spreads; initial/variation margin stress; capital/CCLF allocation; modeled netting sets; direct/sponsored/agent fees.
- Cost, timing and capacity: trade routing decision at quote acceptance; historical public aggregates are lagged and cannot be used as intraday quotes; Constrained by FICC participant access, available repo quote depth, account/entity eligibility and netting-set segregation.

## Future outputs (not generated)
`run_envelope.json` with source hashes/vintages/versions, `eligible_actions.json`, `baseline_metrics.json`, `candidate_metrics.json`, `confidence_intervals.json`, `claim_ledger.md`, `human_review.md`.

## Failure codes and operational controls
`SOURCE_UNLICENSED`, `FUTURE_INFORMATION`, `MISSING_VINTAGE`, `INVALID_UNIT`, `INFEASIBLE_CONSTRAINT`, `EXECUTION_UNAVAILABLE`, `NOT_IDENTIFIED`.
All errors fail closed with explicit reason; no fallback trading. Monitor source lag and policy drift; rollout and rollback require separate reviewed code/CI evidence.
