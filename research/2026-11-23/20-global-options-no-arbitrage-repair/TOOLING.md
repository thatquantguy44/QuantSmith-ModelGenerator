# TOOLING — Arbitrage-Free Equity Volatility Surface Repair Across Markets
**Status:** proposed modules and dependencies; none installed in this PR.

## Domain-specific potential packages
numpy, scipy.optimize, jax, QuantLib. Pin exact compatible versions, lock hashes and document solver tolerances at implementation time; verify package licence and suitable model assumptions.

## Reusable cross-batch library contracts
- `qmg_core.sources.SnapshotSource.load(as_of, licence_class)`: original release and revision lineage.
- `qmg_core.time.AvailabilityIndex.filter(decision_time)`: no-later-than time filter.
- `qmg_core.contracts.EconomicState`: units, eligibility, `US, UK and Japan equity index listed options` market calendar.
- `qmg_core.economics.CostModel`: Surface repairs support quality/risk decisions first; apparent arbitrage cannot be traded without depth and cost.
- `qmg_core.baselines.PolicyComparator`: Per-expiry unconstrained cubic interpolation with clip to bid/ask
- `qmg_core.evals.FalsificationGate`: Constrained repair does not reduce out-of-sample pricing/hedging error or introduces hidden quote crossings.
- `qmg_core.evidence.ClaimLedger`: verifiable external claims versus hypotheses.

## Project-specific package proposal
`src/qmg/research/global_options_no_arbitrage_repair/`: `contracts.py`, `source_adapter.py`, `baseline.py`, `candidate.py`, `objective.py`, `evals.py`, `cli.py`, `tests/test_publication_clock.py`, `tests/test_negative_controls.py`.
Domain input: Time-synchronized option bid/ask, underlying forwards, dividends, exchange calendars, corporate action adjustments. Main model: Static no-arbitrage SVI/SSVI constrained calibration with conservative quote filters. Optional next step: Joint multi-market neural stochastic volatility calibrated to arbitrage constraints and holidays.

## Interface safety
Keep public/paid/private adapters separate; no token strings, client data or scrape-prohibited market data in the repository. Export proposed schema examples with **synthetic rows only**. Runtime and tests are not implemented.
