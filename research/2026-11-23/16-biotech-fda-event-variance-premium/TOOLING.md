# TOOLING — Biotech FDA Catalyst Probability versus Options Event Premium
**Status:** proposed modules and dependencies; none installed in this PR.

## Domain-specific potential packages
pymc, scipy, polars, pydantic. Pin exact compatible versions, lock hashes and document solver tolerances at implementation time; verify package licence and suitable model assumptions.

## Reusable cross-batch library contracts
- `qmg_core.sources.SnapshotSource.load(as_of, licence_class)`: original release and revision lineage.
- `qmg_core.time.AvailabilityIndex.filter(decision_time)`: no-later-than time filter.
- `qmg_core.contracts.EconomicState`: units, eligibility, `US small/mid-cap biotech equity and listed options` market calendar.
- `qmg_core.economics.CostModel`: Biotech option spreads and gap risk severe; define small budget and loss limit before evaluating.
- `qmg_core.baselines.PolicyComparator`: Historical absolute event returns grouped by market cap and indication
- `qmg_core.evals.FalsificationGate`: Conditional probability model fails event-matched calibration or net executable option premium.
- `qmg_core.evidence.ClaimLedger`: verifiable external claims versus hypotheses.

## Project-specific package proposal
`src/qmg/research/biotech_fda_event_variance_premium/`: `contracts.py`, `source_adapter.py`, `baseline.py`, `candidate.py`, `objective.py`, `evals.py`, `cli.py`, `tests/test_publication_clock.py`, `tests/test_negative_controls.py`.
Domain input: FDA event dates, approval histories, pre-event public filings, full options surfaces, equity halt and event-time trades. Main model: Regulatory-document event taxonomy + shrinkage conditional jump model. Optional next step: Hierarchical Bayesian decision-state model and option-neutral density decomposition.

## Interface safety
Keep public/paid/private adapters separate; no token strings, client data or scrape-prohibited market data in the repository. Export proposed schema examples with **synthetic rows only**. Runtime and tests are not implemented.
