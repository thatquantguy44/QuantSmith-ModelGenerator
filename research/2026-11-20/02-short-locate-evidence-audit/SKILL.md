---
name: short-locate-evidence-audit
description: "Reusable research skill for Reg SHO Locate Evidence and Borrow-Capacity Audit Engine; source-time-aware falsifiable economic evaluation. No live trading."
---
# Research skill — Reg SHO Locate Evidence and Borrow-Capacity Audit Engine
## Trigger
When a quant team asks to **Block or escalate a short-sale request if contemporaneous legally qualifying locate evidence or remaining documented quantity is insufficient.** in US equity securities lending and short-sale compliance.
## Required inputs
Legal scope, decision timestamp, short-sale request × account × security × source × event timestamp, fields (Synthetic short-sale order events, documented locate timestamps, source identity, shares remaining, exemptions and post-trade recalls; later private desk records only if approved.), approved source license, trade/operating costs and untouched outcome window.
## Steps
1. Inspect SPEC H1/H0 and Unlike old loan-fee selection correction, tests documentation/quantity compliance and audit proof, not fair value or pricing.
2. Cite official source links, separate publication from effective date; follow Locate documentation and quantity must be timestamped before short sale; revised records cannot retroactively authorize prior orders.
3. Build a synthetic point-in-time fixture with missing, late and contradictory events.
4. Reproduce baseline `End-of-day deterministic locate exception SQL rules`, compare to do-nothing under matched constraints.
5. Prototype `Typed event-sourcing finite-state verification with causal explainability` and retain `Conformal anomaly scoring for ambiguous evidence routed to human review, never autonomous compliance override` only if ablation justifies.
6. Evaluate `prevented invalid requests, false blocks, recall error, audit completion time, p99 latency`; stress Reg SHO exemptions, broker responsibilities and settlement rules require qualified legal interpretation.
7. Apply hard stop: Fails to flag intentionally missing/expired/overused locates on synthetic fixtures or blocks materially more valid trades than comparator.
8. Report cost/capacity and explicit invented ROI sensitivity separately from verified empirical effects.
9. Update HANDOFF with evidence links and red flags; no live integration without human signoff.
## Output contract
Proposed `source_ledger.json`, `pit_manifest.json`, `baseline_metrics.json`, `candidate_metrics.json`, `risk_report.md`, `review_record.md` (not created by this doc PR).
## Failure behavior
Missing data rights or no feasible comparator → BLOCKED; do not fabricate a substitution, source license or outcome.
