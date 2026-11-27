# PLAN — US Small-Cap ATM Equity Issuance Dilution Hazard
**QMG-20261127-11 | B — Domestic/global markets | US small-cap equities | proposal only**
## Architecture
Source adapter → vintage/rights registry → atm-issuance-dilution-hazard state builder → baseline → candidate → matched economic replay → independent gate. Grain: issuer CIK × accession × trading day. Data: 424B prospectuses, 8-K/10-Q share counts, cash burn, issuance disclosures, delisting-adjusted returns. Timing: first dissemination of each accession, next tradable session; quarter issuance outcomes after filings.

## Model sequence
Baseline cash-runway and market-cap logistic hazard; candidate survival model with disclosed program capacity and competing financing events; advanced hierarchical joint issuance-size and event-return model. Estimate on rolling training windows, tune only validation, freeze holdout and cost assumptions. Build a no-action comparator when capacity uncertain. Primary risk: ATM authorization is not execution; reverse splits, delayed quarterly reports and failed issuers. No private data in repo.

## Proposed typed functions
load(as_of, source_ids)->versioned_rows; state(rows, cutoff)->atm-issuance-dilution-hazard decision states; baseline(states)->actions; candidate(states, config)->actions; evaluate(actions, outcomes)->Brier, dilution MAE, event return attribution, false-alert rate; validate() rejects authorization without issuance; reverse split; delisting; duplicate supplement. Map functions to REQ-001–004 and NFR-001/002; report missing inputs rather than fabricate. $100m risk sleeve × 15 bps annual net avoided loss scenario=$150k/year; no alpha assumed measured. Check actual costs/available liquidity before shadow. No implementation yet.
