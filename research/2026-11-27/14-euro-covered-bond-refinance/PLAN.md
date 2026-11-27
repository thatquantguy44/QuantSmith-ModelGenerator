# PLAN — Euro Bank Covered versus Unsecured Refinancing Maturity Wall
**QMG-20261127-14 | B — Domestic/global markets | Euro area bank credit | proposal only**
## Architecture
Source adapter → vintage/rights registry → euro-covered-bond-refinance state builder → baseline → candidate → matched economic replay → independent gate. Grain: issuer × liability class × reporting vintage. Data: covered/unsecured maturities, encumbrance, bank filings, issuance prices, curves, rating history. Timing: filing dissemination before monthly decision; issue prices after actual issuance as outcomes.

## Model sequence
Baseline rating, duration and sovereign spread regression; candidate panel maturity-wall regression with competing liability type; advanced structural joint issuance choice and spread state model. Estimate on rolling training windows, tune only validation, freeze holdout and cost assumptions. Build a no-action comparator when capacity uncertain. Primary risk: ECB aggregates do not establish individual maturity terms; selection into issuance. No private data in repo.

## Proposed typed functions
load(as_of, source_ids)->versioned_rows; state(rows, cutoff)->euro-covered-bond-refinance decision states; baseline(states)->actions; candidate(states, config)->actions; evaluate(actions, outcomes)->spread MAE, gap error, coverage, class-adjusted residual; validate() rejects no issuance censoring; called debt; revised maturities; currency mismatch. Map functions to REQ-001–004 and NFR-001/002; report missing inputs rather than fabricate. $120m credit sleeve × 10 bps net annual risk-selection benefit=$120k/year; no guaranteed liquidity. Check actual costs/available liquidity before shadow. No implementation yet.
