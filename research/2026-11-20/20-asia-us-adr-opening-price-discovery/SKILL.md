---
name: asia-us-adr-opening-price-discovery
description: "Reusable research skill for Asia–US Cross-Listed ADR Opening Auction Information Transfer; source-time-aware falsifiable economic evaluation. No live trading."
---
# Research skill — Asia–US Cross-Listed ADR Opening Auction Information Transfer
## Trigger
When a quant team asks to **Choose hedge and execution timing for US ADR versus home-market overnight fair value.** in US ADRs and Korea/Japan/Taiwan/Hong Kong local shares.
## Required inputs
Legal scope, decision timestamp, ADR × home-market session × US opening-auction timestamp, fields (Issuer depositary receipts ratios, local listings, public filings, FX quote timestamps, US ADR opening auctions, dividends and corporate action history.), approved source license, trade/operating costs and untouched outcome window.
## Steps
1. Inspect SPEC H1/H0 and Prior global covariance regime and FX hedge programs forecast portfolio risk; this models cross-listed single-name auction lead-lag with depositary mechanics.
2. Cite official source links, separate publication from effective date; follow Prevent local-price forward fill across sessions; ratio/corporate actions must be known at the US quote decision time.
3. Build a synthetic point-in-time fixture with missing, late and contradictory events.
4. Reproduce baseline `Last home close × publicly known ADR conversion ratio × contemporaneous FX spot`, compare to do-nothing under matched constraints.
5. Prototype `State-space asynchronous Kalman fair-value update using futures and related peer prices` and retain `Continuous-time latent-price discovery with joint jump and optimal execution inventory control` only if ablation justifies.
6. Evaluate `auction fair-value error, paired realized slippage, inventory risk, settlement/convertibility feasibility`; stress ADR conversion fees, access restrictions, local holidays and stale home quotes create phantom arbitrage.
7. Apply hard stop: No consistent opening execution improvement after financing, foreign exchange, depositary and auction spread costs.
8. Report cost/capacity and explicit invented ROI sensitivity separately from verified empirical effects.
9. Update HANDOFF with evidence links and red flags; no live integration without human signoff.
## Output contract
Proposed `source_ledger.json`, `pit_manifest.json`, `baseline_metrics.json`, `candidate_metrics.json`, `risk_report.md`, `review_record.md` (not created by this doc PR).
## Failure behavior
Missing data rights or no feasible comparator → BLOCKED; do not fabricate a substitution, source license or outcome.
