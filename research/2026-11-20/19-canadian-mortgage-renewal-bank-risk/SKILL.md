---
name: canadian-mortgage-renewal-bank-risk
description: "Reusable research skill for Canadian Mortgage Renewal Cohorts to Bank Credit-Risk Dispersion; source-time-aware falsifiable economic evaluation. No live trading."
---
# Research skill — Canadian Mortgage Renewal Cohorts to Bank Credit-Risk Dispersion
## Trigger
When a quant team asks to **Hedge Canadian bank credit/equity risk using public maturity-cohort mortgage renewal exposure rather than broad unemployment alone.** in Canadian banks, mortgage credit and bank equity/CDS.
## Required inputs
Legal scope, decision timestamp, Canadian mortgage cohort × monthly public release × bank quarterly filing, fields (Bank of Canada public mortgage balances/rates, staff renewal methodology, bank annual/quarterly mortgage disclosures, CAD rate and housing data.), approved source license, trade/operating costs and untouched outcome window.
## Steps
1. Inspect SPEC H1/H0 and Compared with Korean household DSR, this is Canadian *mortgage fixed-rate renewal cohort repricing* versus bank credit loss forecasts.
2. Cite official source links, separate publication from effective date; follow Use released monthly tables and historical market expectations before renewal; a 2025 note's projected 2026 payments are scenario assumptions, not observed outcomes.
3. Build a synthetic point-in-time fixture with missing, late and contradictory events.
4. Reproduce baseline `Bank loss sensitivity to national unemployment and policy rate alone`, compare to do-nothing under matched constraints.
5. Prototype `Vintage-cohort mortgage reset microsimulation from public aggregates` and retain `Hierarchical hazard model linking repricing, prepayment and issuer loan-level exposures` only if ablation justifies.
6. Evaluate `future loss forecast gain, bank-spread risk hedging, sensitivity to vintage assumptions, net hedging cost`; stress Public aggregate cohorts do not identify each bank's borrower vintage distribution or underwriting quality.
7. Apply hard stop: No cross-bank predictive signal after public loan books and unemployment/rate controls, or estimates too wide to act on.
8. Report cost/capacity and explicit invented ROI sensitivity separately from verified empirical effects.
9. Update HANDOFF with evidence links and red flags; no live integration without human signoff.
## Output contract
Proposed `source_ledger.json`, `pit_manifest.json`, `baseline_metrics.json`, `candidate_metrics.json`, `risk_report.md`, `review_record.md` (not created by this doc PR).
## Failure behavior
Missing data rights or no feasible comparator → BLOCKED; do not fabricate a substitution, source license or outcome.
