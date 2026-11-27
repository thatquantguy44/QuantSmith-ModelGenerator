# TOOLING — CCP Member Default Position-Porting Time and Liquidity Optimization
**Status:** proposed modules and dependencies; none installed in this PR.

## Domain-specific potential packages
ortools, simpy, scipy, networkx. Pin exact compatible versions, lock hashes and document solver tolerances at implementation time; verify package licence and suitable model assumptions.

## Reusable cross-batch library contracts
- `qmg_core.sources.SnapshotSource.load(as_of, licence_class)`: original release and revision lineage.
- `qmg_core.time.AvailabilityIndex.filter(decision_time)`: no-later-than time filter.
- `qmg_core.contracts.EconomicState`: units, eligibility, `Global cleared rates and repo portfolios` market calendar.
- `qmg_core.economics.CostModel`: Not a deployable CCP recovery plan; scenario policy must be vetted by legal and risk.
- `qmg_core.baselines.PolicyComparator`: Manual first-available eligible clearing member routing
- `qmg_core.evals.FalsificationGate`: No improvement in adverse default scenarios over conservative porting alternatives or reliance on forbidden client position data.
- `qmg_core.evidence.ClaimLedger`: verifiable external claims versus hypotheses.

## Project-specific package proposal
`src/qmg/research/ccp_member_porting_time_risk/`: `contracts.py`, `source_adapter.py`, `baseline.py`, `candidate.py`, `objective.py`, `evals.py`, `cli.py`, `tests/test_publication_clock.py`, `tests/test_negative_controls.py`.
Domain input: Public CCP rulebooks; synthetic position/eligibility and margin profiles; simulated member outage. Main model: Multi-period mixed-integer stochastic porting/survival flow simulator. Optional next step: Distributionally robust queueing network with correlated member liquidity and stress haircuts.

## Interface safety
Keep public/paid/private adapters separate; no token strings, client data or scrape-prohibited market data in the repository. Export proposed schema examples with **synthetic rows only**. Runtime and tests are not implemented.
