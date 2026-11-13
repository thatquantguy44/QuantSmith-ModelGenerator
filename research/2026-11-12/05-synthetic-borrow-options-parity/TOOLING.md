# TOOLING — Synthetic Borrow Supply via Options Parity
## Proposed project tools (not installed or coded here)
`scipy,cvxpy,pandas`, with pinned versions at implementation time. Validate licensing and numerical solver suitability.
## Shared reusable modules
- `qmg_core.temporal`: effective/published/observed time and immutable vintages.
- `qmg_core.sources`: public versus licensed versus permissioned source checks.
- `qmg_core.economics`: funding, fees, capital, liquidity and execution costs.
- `qmg_core.optimization`: feasibility checks, baselines, solver diagnostics.
- `qmg_core.evaluation`: holdout design, paired policy estimates, leakage tests, bootstrap.
- `qmg_core.provenance`: claim ledger, run manifest, reproducible configuration.
## Idea-specific proposed code
`src/qmg/research/synthetic_borrow_options_parity/contracts.py`, `baseline.py`, `model.py`, `policy.py`, `eval.py`, `cli.py`.
Input grain corresponds to Options bid/ask, dividends, loan fees, stock price, funding, margin and assignment mechanics. Baseline is physical borrow only; candidate is implied financing via corrected put-call parity.
## Source adapters
Use explicit `public`, `licensed`, `private` permission classes and no credential logging. **No runtime or connectors currently exist in this PR.**
