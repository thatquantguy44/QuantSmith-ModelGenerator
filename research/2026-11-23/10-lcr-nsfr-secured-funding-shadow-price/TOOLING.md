# TOOLING — Regulatory LCR/NSFR Shadow Cost of Secured Funding Collateral
**Status:** proposed modules and dependencies; none installed in this PR.

## Domain-specific potential packages
cvxpy, pyomo, scipy, pydantic. Pin exact compatible versions, lock hashes and document solver tolerances at implementation time; verify package licence and suitable model assumptions.

## Reusable cross-batch library contracts
- `qmg_core.sources.SnapshotSource.load(as_of, licence_class)`: original release and revision lineage.
- `qmg_core.time.AvailabilityIndex.filter(decision_time)`: no-later-than time filter.
- `qmg_core.contracts.EconomicState`: units, eligibility, `Global banks; US/EU Basel liquidity reporting frameworks` market calendar.
- `qmg_core.economics.CostModel`: Use only approved internal regulatory measures when available; funding choices constrained by entity/collateral eligibility.
- `qmg_core.baselines.PolicyComparator`: Rank repo offers by quoted rate subject to gross notional limits
- `qmg_core.evals.FalsificationGate`: No cost difference over conservative liquidity-constrained benchmark or unstable/uninterpretable duals.
- `qmg_core.evidence.ClaimLedger`: verifiable external claims versus hypotheses.

## Project-specific package proposal
`src/qmg/research/lcr_nsfr_secured_funding_shadow_price/`: `contracts.py`, `source_adapter.py`, `baseline.py`, `candidate.py`, `objective.py`, `evals.py`, `cli.py`, `tests/test_publication_clock.py`, `tests/test_negative_controls.py`.
Domain input: Public Basel ratio methodology/aggregate trends, synthetic collateral classes, cashflow ladder and legal-entity matrices. Main model: Linear/mixed-integer secured funding allocation with LCR/NSFR dual-price attribution. Optional next step: Scenario-based shadow-price frontier with intraday and quarter-end liquidity risk.

## Interface safety
Keep public/paid/private adapters separate; no token strings, client data or scrape-prohibited market data in the repository. Export proposed schema examples with **synthetic rows only**. Runtime and tests are not implemented.
