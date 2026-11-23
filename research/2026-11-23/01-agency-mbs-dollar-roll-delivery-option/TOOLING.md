# TOOLING — Agency MBS Dollar-Roll Cheapest-to-Deliver Financing Option
**Status:** proposed modules and dependencies; none installed in this PR.

## Domain-specific potential packages
pandas, QuantLib, scipy.optimize, cvxpy. Pin exact compatible versions, lock hashes and document solver tolerances at implementation time; verify package licence and suitable model assumptions.

## Reusable cross-batch library contracts
- `qmg_core.sources.SnapshotSource.load(as_of, licence_class)`: original release and revision lineage.
- `qmg_core.time.AvailabilityIndex.filter(decision_time)`: no-later-than time filter.
- `qmg_core.contracts.EconomicState`: units, eligibility, `United States / agency MBS TBA` market calendar.
- `qmg_core.economics.CostModel`: Market depth and eligible pool inventory limit size; include bid/ask, delivery allocations, financing and clearing margin.
- `qmg_core.baselines.PolicyComparator`: Dollar-roll implied financing vs same-tenor generic repo without delivery-option valuation
- `qmg_core.evals.FalsificationGate`: No stable out-of-sample cost-adjusted advantage over delivery-aware manual baseline at realistic pool eligibility.
- `qmg_core.evidence.ClaimLedger`: verifiable external claims versus hypotheses.

## Project-specific package proposal
`src/qmg/research/agency_mbs_dollar_roll_delivery_option/`: `contracts.py`, `source_adapter.py`, `baseline.py`, `candidate.py`, `objective.py`, `evals.py`, `cli.py`, `tests/test_publication_clock.py`, `tests/test_negative_controls.py`.
Domain input: TBA front/back prices, pools, payups, coupon schedules, specified-pool risk, MBSD netting, EPN eligibility and execution costs. Main model: Constrained pool-delivery optimizer with observable pool financing carry and roll prices. Optional next step: Stochastic pool quality and delivery-selection real-options game with cheapest-deliverable simulation.

## Interface safety
Keep public/paid/private adapters separate; no token strings, client data or scrape-prohibited market data in the repository. Export proposed schema examples with **synthetic rows only**. Runtime and tests are not implemented.
