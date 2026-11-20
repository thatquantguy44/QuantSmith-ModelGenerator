---
name: etf-basket-stockloan-flow
description: "Reusable research skill for ETF Creation/Redemption Basket Shock to Stock-Loan Supply; source-time-aware falsifiable economic evaluation. No live trading."
---
# Research skill — ETF Creation/Redemption Basket Shock to Stock-Loan Supply
## Trigger
When a quant team asks to **Reserve lendable constituent supply ahead of known or forecasted ETF in-kind redemption/creation windows.** in US equity ETFs and underlying stock loan.
## Required inputs
Legal scope, decision timestamp, ETF × constituent × creation/redemption day × publication time, fields (ETF disclosed holdings and creation units, public filings, official membership events, licensed AP basket/flows and loan availability for later study.), approved source license, trade/operating costs and untouched outcome window.
## Steps
1. Inspect SPEC H1/H0 and Distinct from synthetic borrow put-call parity and owner's co-withdrawal risk; identifies ETF primary basket supply as separate driver.
2. Cite official source links, separate publication from effective date; follow Only baskets available to a decision-maker before ETF order cutoff may be used; end-of-day holding reports are not morning baskets.
3. Build a synthetic point-in-time fixture with missing, late and contradictory events.
4. Reproduce baseline `Change in ETF shares outstanding plus index-event dummy`, compare to do-nothing under matched constraints.
5. Prototype `Hierarchical event study with issuer-basket aggregation and controls` and retain `Instrumented flow shock model addressing ETF price-demand endogeneity` only if ablation justifies.
6. Evaluate `inventory forecast MAE, short availability calibration, incremental net inventory carry, execution slippage`; stress Most executable AP basket details and actual stock-loan supply are not public.
7. Apply hard stop: No incremental held-out inventory signal after availability alignment and underlying stock flow controls.
8. Report cost/capacity and explicit invented ROI sensitivity separately from verified empirical effects.
9. Update HANDOFF with evidence links and red flags; no live integration without human signoff.
## Output contract
Proposed `source_ledger.json`, `pit_manifest.json`, `baseline_metrics.json`, `candidate_metrics.json`, `risk_report.md`, `review_record.md` (not created by this doc PR).
## Failure behavior
Missing data rights or no feasible comparator → BLOCKED; do not fabricate a substitution, source license or outcome.
