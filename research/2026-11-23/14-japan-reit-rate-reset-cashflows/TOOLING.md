# TOOLING — Japanese Real-Estate Equity Cash-Flow Sensitivity to BOJ Rate Normalization
**Status:** proposed modules and dependencies; none installed in this PR.

## Domain-specific potential packages
pandas, polars, statsmodels, pydantic. Pin exact compatible versions, lock hashes and document solver tolerances at implementation time; verify package licence and suitable model assumptions.

## Reusable cross-batch library contracts
- `qmg_core.sources.SnapshotSource.load(as_of, licence_class)`: original release and revision lineage.
- `qmg_core.time.AvailabilityIndex.filter(decision_time)`: no-later-than time filter.
- `qmg_core.contracts.EconomicState`: units, eligibility, `Japan J-REITs and commercial real estate` market calendar.
- `qmg_core.economics.CostModel`: J-REIT constituent liquidity, FX hedge and foreign-investor restrictions limit realized capacity.
- `qmg_core.baselines.PolicyComparator`: Market REIT index duration and price-to-NAV score
- `qmg_core.evals.FalsificationGate`: No incremental post-rate-shift forecast after issuer fixed-effects and NAV-duration controls.
- `qmg_core.evidence.ClaimLedger`: verifiable external claims versus hypotheses.

## Project-specific package proposal
`src/qmg/research/japan_reit_rate_reset_cashflows/`: `contracts.py`, `source_adapter.py`, `baseline.py`, `candidate.py`, `objective.py`, `evals.py`, `cli.py`, `tests/test_publication_clock.py`, `tests/test_negative_controls.py`.
Domain input: BOJ rate time series, J-REIT bond/debt disclosures, rent index, total returns and market-based NAV. Main model: Disclosure-derived maturity-wall factor with event-based hedged return regressions. Optional next step: Tenant lease rollover and financing reset structural cash-flow model.

## Interface safety
Keep public/paid/private adapters separate; no token strings, client data or scrape-prohibited market data in the repository. Export proposed schema examples with **synthetic rows only**. Runtime and tests are not implemented.
