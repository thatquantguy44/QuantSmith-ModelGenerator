# TOOLING — Corporate Bond Securities Lending from CDS Basis Hedge Demand
**Status:** proposed modules and dependencies; none installed in this PR.

## Domain-specific potential packages
polars, statsmodels, lifelines, cvxpy. Pin exact compatible versions, lock hashes and document solver tolerances at implementation time; verify package licence and suitable model assumptions.

## Reusable cross-batch library contracts
- `qmg_core.sources.SnapshotSource.load(as_of, licence_class)`: original release and revision lineage.
- `qmg_core.time.AvailabilityIndex.filter(decision_time)`: no-later-than time filter.
- `qmg_core.contracts.EconomicState`: units, eligibility, `US and European investment-grade / high-yield credit` market calendar.
- `qmg_core.economics.CostModel`: Bond borrow capacity and transaction costs can overwhelm narrow basis; never equate public volume with tradable borrow.
- `qmg_core.baselines.PolicyComparator`: Trailing borrower request count and issue-size utilization
- `qmg_core.evals.FalsificationGate`: Estimated basis effects fail paired holdouts or increase rejected locates after slippage and liquidity controls.
- `qmg_core.evidence.ClaimLedger`: verifiable external claims versus hypotheses.

## Project-specific package proposal
`src/qmg/research/corporate_bond_cds_basis_borrow_demand/`: `contracts.py`, `source_adapter.py`, `baseline.py`, `candidate.py`, `objective.py`, `evals.py`, `cli.py`, `tests/test_publication_clock.py`, `tests/test_negative_controls.py`.
Domain input: CUSIP-level corporate bond lending fees/locates, CDS curves, TRACE trade activity, issue amount, corporate actions. Main model: Matched event study plus borrow-arrival hazard conditional on CDS-bond basis. Optional next step: Structural joint CDS/bond market-maker inventory model with selection-corrected demand.

## Interface safety
Keep public/paid/private adapters separate; no token strings, client data or scrape-prohibited market data in the repository. Export proposed schema examples with **synthetic rows only**. Runtime and tests are not implemented.
