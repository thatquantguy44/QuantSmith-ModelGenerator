# TOOLING — Collateral Reuse Chain Stress Testing
## Proposed project tools (not installed or coded here)
`networkx,scipy.sparse,simpy`, with pinned versions at implementation time. Validate licensing and numerical solver suitability.
## Shared reusable modules
- `qmg_core.temporal`: effective/published/observed time and immutable vintages.
- `qmg_core.sources`: public versus licensed versus permissioned source checks.
- `qmg_core.economics`: funding, fees, capital, liquidity and execution costs.
- `qmg_core.optimization`: feasibility checks, baselines, solver diagnostics.
- `qmg_core.evaluation`: holdout design, paired policy estimates, leakage tests, bootstrap.
- `qmg_core.provenance`: claim ledger, run manifest, reproducible configuration.
## Idea-specific proposed code
`src/qmg/research/collateral_reuse_stress/contracts.py`, `baseline.py`, `model.py`, `policy.py`, `eval.py`, `cli.py`.
Input grain corresponds to Source provenance, permissioned reuse contracts, collateral movements, haircut and margin events. Baseline is gross collateral stock and static stress; candidate is legal reuse network input-output simulation.
## Source adapters
Use explicit `public`, `licensed`, `private` permission classes and no credential logging. **No runtime or connectors currently exist in this PR.**
