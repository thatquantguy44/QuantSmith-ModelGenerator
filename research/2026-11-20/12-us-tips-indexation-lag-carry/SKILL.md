---
name: us-tips-indexation-lag-carry
description: "Reusable research skill for US TIPS CPI Indexation-Lag Carry and Breakeven Calendar Surface; source-time-aware falsifiable economic evaluation. No live trading."
---
# Research skill — US TIPS CPI Indexation-Lag Carry and Breakeven Calendar Surface
## Trigger
When a quant team asks to **Select TIPS versus nominal duration-hedged exposure around CPI index-ratio carry windows.** in US TIPS, nominal Treasuries, inflation swaps.
## Required inputs
Legal scope, decision timestamp, TIPS CUSIP × CPI/index-ratio effective date × decision timestamp, fields (Treasury official daily TIPS index ratios/CPI, vintage BLS CPI, nominal/TIPS quotes, issue terms, accrued interest.), approved source license, trade/operating costs and untouched outcome window.
## Steps
1. Inspect SPEC H1/H0 and Prior US-Euro sovereign curve shock model decomposes release shocks; this prices U.S. issue-specific TIPS CPI indexation carry.
2. Cite official source links, separate publication from effective date; follow Daily index ratios can be forecast only from already published reference CPI; preserve first release and later corrections.
3. Build a synthetic point-in-time fixture with missing, late and contradictory events.
4. Reproduce baseline `Duration-matched TIPS-minus-nominal bond without CPI-calendar signal`, compare to do-nothing under matched constraints.
5. Prototype `Deterministic index-ratio accrual and liquidity-factor attribution` and retain `State-space real/nominal curve with stochastic CPI surprise and inflation floor convexity` only if ablation justifies.
6. Evaluate `hedge tracking error, information ratio net of costs, index replication error, carry decomposition residual`; stress Illiquid issue quotations, inflation floor optionality, unrevised CPI data and seasonality overfit.
7. Apply hard stop: Improvement vanishes versus a carry-only and time-matched duration hedge after execution spread costs.
8. Report cost/capacity and explicit invented ROI sensitivity separately from verified empirical effects.
9. Update HANDOFF with evidence links and red flags; no live integration without human signoff.
## Output contract
Proposed `source_ledger.json`, `pit_manifest.json`, `baseline_metrics.json`, `candidate_metrics.json`, `risk_report.md`, `review_record.md` (not created by this doc PR).
## Failure behavior
Missing data rights or no feasible comparator → BLOCKED; do not fabricate a substitution, source license or outcome.
