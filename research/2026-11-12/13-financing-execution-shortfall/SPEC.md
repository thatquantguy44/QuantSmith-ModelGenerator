# SPEC — Financing Execution Shortfall Model
**Status:** draft for approval · **ID:** QMG-20261112-13
## Problem and falsifiable hypothesis
Pricing execution can deteriorate between request, quote, acceptance, booking and settlement.
- **Decision:** diagnose where quoted financing economics leak before completed settlement.
- **H1:** Point-in-time causal leakage attribution discovers correctable costs over a quote-only baseline.
- **H0:** a feasible cost-inclusive implementation of `executed spread minus indicative quote` is not materially worse than the candidate.
## Mathematical formulation
```text
shortfall=realized_cost-decision_cost=market_move+delay+negotiation+settlement
```
Units, exposure direction and feasibility constraints must be signed off before numerical implementation.
## Data contract
**Required fields:** Timestamped RFQs, quotes, fill/rejects, booked fees, market moves and settlement. Grain: event time × instrument × counterparty/cohort, normalized for diagnose where quoted financing economics leak before completed settlement. Preserve event timestamp, information-available timestamp, source/vintage, legal permissions, missingness and revision history.
## Requirements
- **REQ-001:** represent the decision `diagnose where quoted financing economics leak before completed settlement` and legal/operational feasibility.
- **REQ-002:** implement deterministic cost-inclusive baseline `executed spread minus indicative quote`.
- **REQ-003:** define testable candidate `cost-inclusive execution shortfall event ledger` against the same opportunities.
- **REQ-004:** report `bps slippage, recovered P&L, latency and fill rate` with uncertainty and capacity.
- **NFR-001:** no lookahead; deterministic seed, fixture and versioned parameters.
- **NFR-002:** reject restricted or unlicensed data, live trades and unauthorized actions.
## Acceptance criteria
- **AC-001** REQ-001: correct temporal and eligibility schema on synthetic fixtures.
- **AC-002** REQ-002: baseline cost and constraint tests pass deterministically.
- **AC-003** REQ-003: matched holdout candidate evaluation is reproducible.
- **AC-004** REQ-004: uncertainty, tail cases and net economics are reported.
- **AC-005** NFR-001/002: lookahead and confidentiality checks reject violations.
## Risks, non-goals and falsification
**RISK-001:** quotes may be non-executable; client selection creates bias. **RISK-002:** unobserved transactions, misestimated operating costs or regime instability. No production execution or empirically proven ROI in scope. **Reject H1** if the apparent advantage vanishes after costs, feasible constraints or holdout evaluation. Illustration 2–4× is not verified.
