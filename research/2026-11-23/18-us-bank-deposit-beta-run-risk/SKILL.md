---
name: us-bank-deposit-beta-run-risk
description: "US Bank Deposit Beta and Mark-to-Market Securities Run Risk: reproducible, source-timed quantitative research design with independent falsification."
---
# SKILL — US Bank Deposit Beta and Mark-to-Market Securities Run Risk
## When to use
When evaluating: Assess which banks face funding-cost and securities-loss convexity under uninsured deposit migration.

## Preconditions
Source entitlement, as-of clock and accounting convention for FDIC bank Call Reports, quarterly uninsured deposits, HTM/AFS loss fields, benchmark rates, bank equity CDS; a defined decision and costed baseline.

## Procedure
1. Freeze H1: A joint deposit-beta and securities mark-to-market gap predicts earnings/credit deterioration better than uninsured deposit percentage.; define H0 with cost-inclusive `Uninsured deposit share plus book capital ratio`.
2. Verify official pages and specific historical source versions. Quarter-end balances become usable only at the first public Call Report publication, not period end.
3. Build deterministic synthetic fixtures including: Quarterly revisions, mergers, bank survivorship and missing bank-specific deposit pricing..
4. Implement the baseline before trying `Hierarchical deposit beta estimation plus accounting-based duration stress`.
5. Test `Agent-based depositor migration with liquidity haircut and contagion sensitivity` only if the simpler candidate survives.
6. Reconstruct economic costs and capacity: Large regional bank equity/cash bonds viable; small banks thin, CDS pricing inaccessible and not required for public proxy..
7. Report Next-quarter NII loss, downside rank precision, capital shortfall, sector-neutral return IC plus negative-control confidence bounds.
8. Stop if: No incremental forecast versus capital/deposit mix baseline after strict public release lag..
9. Prepare code hash, evidence ledger, and independent human review. No trading.

## Outputs
Proposed `manifest.json`, `source_ledger.json`, `baseline.json`, `candidate.json`, `robustness.md`, `decision.md`.
**These output files do not exist in this specification-only batch.**
## Reusability
Reuse point-in-time source gates, mathematical feasibility, cost contracts and paired economic evaluation; keep us-bank-deposit-beta-run-risk domain-specific features isolated.
