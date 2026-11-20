---
name: eu-ets-auction-carbon-carry
description: "Reusable research skill for EU ETS Auction Supply Revision and Carbon Futures Carry; source-time-aware falsifiable economic evaluation. No live trading."
---
# Research skill — EU ETS Auction Supply Revision and Carbon Futures Carry
## Trigger
When a quant team asks to **Hedge EUA futures calendar spreads against only announced changes in auction volume and verified-emissions obligations.** in EU carbon allowances (EUA), European power utilities.
## Required inputs
Legal scope, decision timestamp, EU ETS auction calendar publication × allowance futures tenor × exchange quote timestamp, fields (European Commission vintage auction calendars, Union Registry verified emissions/compliance, dated policy changes, EUA/power/gas contract prices.), approved source license, trade/operating costs and untouched outcome window.
## Steps
1. Inspect SPEC H1/H0 and Not prior European gas storage deliverability; models ETS allowance auction policy supply and carbon forward carry.
2. Cite official source links, separate publication from effective date; follow 2027 auction schedule announced Jul 30 2026; 2025 compliance data public Oct 5 2026; only released data at as-of permitted.
3. Build a synthetic point-in-time fixture with missing, late and contradictory events.
4. Reproduce baseline `Calendar-month fixed seasonal allowance spread`, compare to do-nothing under matched constraints.
5. Prototype `Event study of auction schedule revisions and futures risk factors` and retain `Partial equilibrium allowance banking model with endogenous industrial abatement and policy scenarios` only if ablation justifies.
6. Evaluate `EUA spread basis MAE, hedged risk reduction, net carry after fees, low-liquidity scenario loss`; stress Policy revision expectations may be priced before official publication; futures/Registry coverage not contemporaneous.
7. Apply hard stop: No out-of-sample spread forecast or hedge benefit net of spreads after matched energy factors.
8. Report cost/capacity and explicit invented ROI sensitivity separately from verified empirical effects.
9. Update HANDOFF with evidence links and red flags; no live integration without human signoff.
## Output contract
Proposed `source_ledger.json`, `pit_manifest.json`, `baseline_metrics.json`, `candidate_metrics.json`, `risk_report.md`, `review_record.md` (not created by this doc PR).
## Failure behavior
Missing data rights or no feasible comparator → BLOCKED; do not fabricate a substitution, source license or outcome.
