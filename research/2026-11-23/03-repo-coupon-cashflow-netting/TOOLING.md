# TOOLING — Repo Coupon and Principal Event Cash-Flow Netting Scheduler
**Status:** proposed modules and dependencies; none installed in this PR.

## Domain-specific potential packages
ortools, cvxpy, networkx, pandas. Pin exact compatible versions, lock hashes and document solver tolerances at implementation time; verify package licence and suitable model assumptions.

## Reusable cross-batch library contracts
- `qmg_core.sources.SnapshotSource.load(as_of, licence_class)`: original release and revision lineage.
- `qmg_core.time.AvailabilityIndex.filter(decision_time)`: no-later-than time filter.
- `qmg_core.contracts.EconomicState`: units, eligibility, `US Treasuries, agencies and multi-currency repo` market calendar.
- `qmg_core.economics.CostModel`: Savings limited to payments legally eligible for netting; reconciliation costs, daylight overdraft fees and solver latency included.
- `qmg_core.baselines.PolicyComparator`: Gross independent payment processing with static buffer
- `qmg_core.evals.FalsificationGate`: No capacity-adjusted cost reduction versus pre-netted conventional operations or violations of payment rights.
- `qmg_core.evidence.ClaimLedger`: verifiable external claims versus hypotheses.

## Project-specific package proposal
`src/qmg/research/repo_coupon_cashflow_netting/`: `contracts.py`, `source_adapter.py`, `baseline.py`, `candidate.py`, `objective.py`, `evals.py`, `cli.py`, `tests/test_publication_clock.py`, `tests/test_negative_controls.py`.
Domain input: Public bond schedules, ex-coupon dates, settlement calendars, synthetic counterparties and netting agreements. Main model: Mixed-integer liquidity scheduling with eligibility/netting-set constraints. Optional next step: Stochastic event-flow MPC with missed payment penalties and legal-entity netting restrictions.

## Interface safety
Keep public/paid/private adapters separate; no token strings, client data or scrape-prohibited market data in the repository. Export proposed schema examples with **synthetic rows only**. Runtime and tests are not implemented.
