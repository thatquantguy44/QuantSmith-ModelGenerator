# SPEC — Intraday Collateral Liquidity Forecasting via Queueing Theory
**Status:** draft for approval · **ID:** QMG-20261112-03
## Problem and falsifiable hypothesis
Collateral calls arrive asynchronously and compete for limited settlement processing capacity.
- **Decision:** size buffer and prioritize arriving collateral obligations.
- **H1:** Queue-aware controls lower buffer expense without increasing missed margin deadlines.
- **H0:** a feasible cost-inclusive implementation of `fixed intraday liquidity reserve` is not materially worse than the candidate.
## Mathematical formulation
```text
Q(t+1)=max(0,Q(t)+A(t)-service(t)); min_B E[c_f B+c_s(Q-B)^+]
```
Units, exposure direction and feasibility constraints must be signed off before numerical implementation.
## Data contract
**Required fields:** Intraday margin calls, settlement timestamps, queue lengths, cash/collateral buffers, fails. Grain: event time × instrument × counterparty/cohort, normalized for size buffer and prioritize arriving collateral obligations. Preserve event timestamp, information-available timestamp, source/vintage, legal permissions, missingness and revision history.
## Requirements
- **REQ-001:** represent the decision `size buffer and prioritize arriving collateral obligations` and legal/operational feasibility.
- **REQ-002:** implement deterministic cost-inclusive baseline `fixed intraday liquidity reserve`.
- **REQ-003:** define testable candidate `stochastic queueing and priority model` against the same opportunities.
- **REQ-004:** report `liquidity buffer cost, p99 delay, shortfalls and failures` with uncertainty and capacity.
- **NFR-001:** no lookahead; deterministic seed, fixture and versioned parameters.
- **NFR-002:** reject restricted or unlicensed data, live trades and unauthorized actions.
## Acceptance criteria
- **AC-001** REQ-001: correct temporal and eligibility schema on synthetic fixtures.
- **AC-002** REQ-002: baseline cost and constraint tests pass deterministically.
- **AC-003** REQ-003: matched holdout candidate evaluation is reproducible.
- **AC-004** REQ-004: uncertainty, tail cases and net economics are reported.
- **AC-005** NFR-001/002: lookahead and confidentiality checks reject violations.
## Risks, non-goals and falsification
**RISK-001:** timestamp quality and hidden queue-priority rules. **RISK-002:** unobserved transactions, misestimated operating costs or regime instability. No production execution or empirically proven ROI in scope. **Reject H1** if the apparent advantage vanishes after costs, feasible constraints or holdout evaluation. Illustration 3–5× is not verified.
