# TOOLING — Borrow Scarcity Causal Effect on Equity Market-Maker Quoted Depth
**Status:** proposed modules and dependencies; none installed in this PR.

## Domain-specific potential packages
linearmodels, statsmodels, polars, econml. Pin exact compatible versions, lock hashes and document solver tolerances at implementation time; verify package licence and suitable model assumptions.

## Reusable cross-batch library contracts
- `qmg_core.sources.SnapshotSource.load(as_of, licence_class)`: original release and revision lineage.
- `qmg_core.time.AvailabilityIndex.filter(decision_time)`: no-later-than time filter.
- `qmg_core.contracts.EconomicState`: units, eligibility, `US equities and select developed markets` market calendar.
- `qmg_core.economics.CostModel`: Not an unconditional trading signal; capacity depends on quote depth and borrow clearance, include adverse selection.
- `qmg_core.baselines.PolicyComparator`: Spread/depth forecasting using only realized volatility and market cap
- `qmg_core.evals.FalsificationGate`: No pre-registered effect with valid pretrends/instruments or effect only on illiquid untradeable names.
- `qmg_core.evidence.ClaimLedger`: verifiable external claims versus hypotheses.

## Project-specific package proposal
`src/qmg/research/borrow_scarcity_equity_market_depth/`: `contracts.py`, `source_adapter.py`, `baseline.py`, `candidate.py`, `objective.py`, `evals.py`, `cli.py`, `tests/test_publication_clock.py`, `tests/test_negative_controls.py`.
Domain input: Borrow availability and fees, market quotes/trades, issuer event calendars and exclusion instruments. Main model: Matched differences-in-differences/event-time instrumental analysis. Optional next step: Structural market-maker inventory equilibrium with dynamic borrowing constraint.

## Interface safety
Keep public/paid/private adapters separate; no token strings, client data or scrape-prohibited market data in the repository. Export proposed schema examples with **synthetic rows only**. Runtime and tests are not implemented.
