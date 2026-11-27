# TOOLING — Fed Standing Repo Facility as a Funding-Stress Option Exercise Signal
**Status:** proposed modules and dependencies; none installed in this PR.

## Domain-specific potential packages
statsmodels, sklearn, polars, pydantic. Pin exact compatible versions, lock hashes and document solver tolerances at implementation time; verify package licence and suitable model assumptions.

## Reusable cross-batch library contracts
- `qmg_core.sources.SnapshotSource.load(as_of, licence_class)`: original release and revision lineage.
- `qmg_core.time.AvailabilityIndex.filter(decision_time)`: no-later-than time filter.
- `qmg_core.contracts.EconomicState`: units, eligibility, `US overnight secured funding` market calendar.
- `qmg_core.economics.CostModel`: Research output is risk-monitoring, not direct trading opportunity; facility eligibility and costs differ by participant.
- `qmg_core.baselines.PolicyComparator`: SOFR-GC spread threshold with no SRF information
- `qmg_core.evals.FalsificationGate`: No holdout information gain after timing correction, or false positives overwhelm funding buffer costs.
- `qmg_core.evidence.ClaimLedger`: verifiable external claims versus hypotheses.

## Project-specific package proposal
`src/qmg/research/fed_srf_funding_stress_option/`: `contracts.py`, `source_adapter.py`, `baseline.py`, `candidate.py`, `objective.py`, `evals.py`, `cli.py`, `tests/test_publication_clock.py`, `tests/test_negative_controls.py`.
Domain input: Official SRF accepted/submitted quantities, summary rates, SOFR, OFR cleared/triparty repo aggregates. Main model: Event-conditioned calibrated logistic hazard with lag-safe publication ledger. Optional next step: Structural real-option exercise mapping latent facility usage and dealer cash constraints.

## Interface safety
Keep public/paid/private adapters separate; no token strings, client data or scrape-prohibited market data in the repository. Export proposed schema examples with **synthetic rows only**. Runtime and tests are not implemented.
