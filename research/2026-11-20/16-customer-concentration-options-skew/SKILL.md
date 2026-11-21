---
name: customer-concentration-options-skew
description: "Reusable research skill for Issuer Customer-Concentration Disclosure to Earnings Options Skew; source-time-aware falsifiable economic evaluation. No live trading."
---
# Research skill — Issuer Customer-Concentration Disclosure to Earnings Options Skew
## Trigger
When a quant team asks to **Hedge customer-loss jump risk in companies with concentrated customers using explicitly costed options structures.** in US listed single-name equity options and SEC 10-K/10-Q issuers.
## Required inputs
Legal scope, decision timestamp, issuer accepted filing × reported customer share × options quote timestamp, fields (SEC EDGAR original issuer filings, customer concentration disclosures, single-stock option surface, earnings calendar, liquidity and corporate actions.), approved source license, trade/operating costs and untouched outcome window.
## Steps
1. Inspect SPEC H1/H0 and Prior Japan buyback execution, AI capex and global factors differ from customer-dependent equity jump risk around original filings.
2. Cite official source links, separate publication from effective date; follow Use SEC acceptance timestamps and first published disclosure, not retroactive tagged XBRL after amended filings.
3. Build a synthetic point-in-time fixture with missing, late and contradictory events.
4. Reproduce baseline `Size/leverage/industry/earnings event-only option skew estimator`, compare to do-nothing under matched constraints.
5. Prototype `Censored-disclosure panel with inverse observation probability adjustment` and retain `Jump-diffusion structural model of concentrated-customer exit hazard` only if ablation justifies.
6. Evaluate `post-filing skew residual, risk hedge efficiency, delta-neutral net performance and disclosure coverage`; stress Customer concentrations may be anonymized and nonrandomly omitted; options trade data can be illiquid.
7. Apply hard stop: No post-filing incremental skew or hedge gain beyond conventional earnings-related jump risk.
8. Report cost/capacity and explicit invented ROI sensitivity separately from verified empirical effects.
9. Update HANDOFF with evidence links and red flags; no live integration without human signoff.
## Output contract
Proposed `source_ledger.json`, `pit_manifest.json`, `baseline_metrics.json`, `candidate_metrics.json`, `risk_report.md`, `review_record.md` (not created by this doc PR).
## Failure behavior
Missing data rights or no feasible comparator → BLOCKED; do not fabricate a substitution, source license or outcome.
