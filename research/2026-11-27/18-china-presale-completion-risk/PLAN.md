# PLAN — China Developer Presale Cash-Conversion and Completion Risk
**QMG-20261127-18 | B — Domestic/global markets | China property developers and Asian credit | proposal only**
## Architecture
Source adapter → vintage/rights registry → china-presale-completion-risk state builder → baseline → candidate → matched economic replay → independent gate. Grain: developer × reporting quarter / national monthly release. Data: sales floor area, deposits/advance receipts, completed/started floor area, issuer cash and debt, escrow restrictions. Timing: first NBS report and issuer filing dissemination, convert cumulative series only using same vintage.

## Model sequence
Baseline leverage and sales growth hazard; candidate stock-flow gap and competing-risk survival; advanced hierarchical partially identified funding gaps with escrow scenarios. Estimate on rolling training windows, tune only validation, freeze holdout and cost assumptions. Build a no-action comparator when capacity uncertain. Primary risk: national aggregate cannot be attributed to specific developers; offshore/onshore exposure and escrow uncertain. No private data in repo.

## Proposed typed functions
load(as_of, source_ids)->versioned_rows; state(rows, cutoff)->china-presale-completion-risk decision states; baseline(states)->actions; candidate(states, config)->actions; evaluate(actions, outcomes)->distress Brier, calibration, completion error, uncertainty width; validate() rejects cumulative reset January, revised comparable basis, negative cash, delisted issuers. Map functions to REQ-001–004 and NFR-001/002; report missing inputs rather than fabricate. $100m credit risk sleeve × 12 bps annual avoided-loss scenario=$120k/year, not observed default savings. Check actual costs/available liquidity before shadow. No implementation yet.
