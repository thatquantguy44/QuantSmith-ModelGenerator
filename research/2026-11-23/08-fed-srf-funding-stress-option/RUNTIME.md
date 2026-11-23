# RUNTIME — Fed Standing Repo Facility as a Funding-Stress Option Exercise Signal
**PROPOSED ONLY. The executable modules and commands below are not currently available.**

## Package/entrypoint
`qmg.research.fed_srf_funding_stress_option.cli`

## Proposed typed YAML keys
`as_of_utc, decision_time, market_timezone, calendar, source_allowlist, licence_class, data_versions, embargo_days, train_window, test_window, legal_constraints, cost_model, random_seed, artifact_dir`.

## Future CLI examples (will fail until implemented)
```bash
python -m qmg.research.fed_srf_funding_stress_option.cli validate --config configs/example.yml --synthetic
python -m qmg.research.fed_srf_funding_stress_option.cli baseline --config configs/example.yml --synthetic
python -m qmg.research.fed_srf_funding_stress_option.cli research --config configs/example.yml --holdout
```

## Proposed immutable outputs
`run_manifest.json`, `license_check.json`, `publication_clock.json`, `baseline_economics.json`, `candidate_economics.json`, `failed_controls.json`, `signed_review.md`.

## Error contract
`RIGHTS_BLOCKED`, `FUTURE_INFORMATION`, `UNCLEARED_ELIGIBILITY`, `NONEXECUTABLE_BASELINE`, `UNIDENTIFIABLE_CAUSAL_EFFECT`, `FAILED_FALSIFICATION` fail closed. Resource use, performance and model drift must be measured before any operational use.
