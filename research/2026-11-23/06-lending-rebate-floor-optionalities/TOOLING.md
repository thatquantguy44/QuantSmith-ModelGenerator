# TOOLING — Securities Lending Cash Rebate Floor Optionality in Low-Rate Regimes
**Status:** proposed modules and dependencies; none installed in this PR.

## Domain-specific potential packages
QuantLib, scipy, pydantic, numpy. Pin exact compatible versions, lock hashes and document solver tolerances at implementation time; verify package licence and suitable model assumptions.

## Reusable cross-batch library contracts
- `qmg_core.sources.SnapshotSource.load(as_of, licence_class)`: original release and revision lineage.
- `qmg_core.time.AvailabilityIndex.filter(decision_time)`: no-later-than time filter.
- `qmg_core.contracts.EconomicState`: units, eligibility, `EUR, CHF, JPY and USD cash-collateralized securities lending` market calendar.
- `qmg_core.economics.CostModel`: Profit only if floors contractually negotiated; hedge notional and floor illiquidity restrict scale.
- `qmg_core.baselines.PolicyComparator`: Static contractual rebate minus benchmark with no optionality
- `qmg_core.evals.FalsificationGate`: Valuation adds no meaningful incremental pricing accuracy to conservative quoted-fee schedules.
- `qmg_core.evidence.ClaimLedger`: verifiable external claims versus hypotheses.

## Project-specific package proposal
`src/qmg/research/lending_rebate_floor_optionalities/`: `contracts.py`, `source_adapter.py`, `baseline.py`, `candidate.py`, `objective.py`, `evals.py`, `cli.py`, `tests/test_publication_clock.py`, `tests/test_negative_controls.py`.
Domain input: Historical overnight benchmarks, collateral currency curves, cash balances, contract rebate-floor clauses. Main model: Rate-tree floor valuation and curve calibration with contract clause parser. Optional next step: Multi-currency short-rate stochastic volatility and correlated collateral run-off scenario valuation.

## Interface safety
Keep public/paid/private adapters separate; no token strings, client data or scrape-prohibited market data in the repository. Export proposed schema examples with **synthetic rows only**. Runtime and tests are not implemented.
