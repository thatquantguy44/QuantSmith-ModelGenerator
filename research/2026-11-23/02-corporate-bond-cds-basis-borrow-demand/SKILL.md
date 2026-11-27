---
name: corporate-bond-cds-basis-borrow-demand
description: "Corporate Bond Securities Lending from CDS Basis Hedge Demand: reproducible, source-timed quantitative research design with independent falsification."
---
# SKILL — Corporate Bond Securities Lending from CDS Basis Hedge Demand
## When to use
When evaluating: Allocate bond lending supply to CDS-bond basis hedging demand with counterparty and liquidity limits.

## Preconditions
Source entitlement, as-of clock and accounting convention for CUSIP-level corporate bond lending fees/locates, CDS curves, TRACE trade activity, issue amount, corporate actions; a defined decision and costed baseline.

## Procedure
1. Freeze H1: CDS-bond basis dislocations predict incremental observable bond borrowing demand after conditioning on issue float, liquidity and credit stress.; define H0 with cost-inclusive `Trailing borrower request count and issue-size utilization`.
2. Verify official pages and specific historical source versions. CDS and cash-bond spreads only after published executable quote times; lending fills observed subsequently.
3. Build deterministic synthetic fixtures including: Non-executable CDS quotes, bond TRACE delay and endogeneity of credit distress..
4. Implement the baseline before trying `Matched event study plus borrow-arrival hazard conditional on CDS-bond basis`.
5. Test `Structural joint CDS/bond market-maker inventory model with selection-corrected demand` only if the simpler candidate survives.
6. Reconstruct economic costs and capacity: Bond borrow capacity and transaction costs can overwhelm narrow basis; never equate public volume with tradable borrow..
7. Report Borrow-arrival log score, realized net fee improvement, stale quote rate and borrow supply capacity plus negative-control confidence bounds.
8. Stop if: Estimated basis effects fail paired holdouts or increase rejected locates after slippage and liquidity controls..
9. Prepare code hash, evidence ledger, and independent human review. No trading.

## Outputs
Proposed `manifest.json`, `source_ledger.json`, `baseline.json`, `candidate.json`, `robustness.md`, `decision.md`.
**These output files do not exist in this specification-only batch.**
## Reusability
Reuse point-in-time source gates, mathematical feasibility, cost contracts and paired economic evaluation; keep corporate-bond-cds-basis-borrow-demand domain-specific features isolated.
