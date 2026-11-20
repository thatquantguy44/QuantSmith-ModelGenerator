---
name: japan-fx-intervention-persistence
description: "Reusable research skill for Japan FX Intervention Impact and Option-Skew Persistence; source-time-aware falsifiable economic evaluation. No live trading."
---
# Research skill — Japan FX Intervention Impact and Option-Skew Persistence
## Trigger
When a quant team asks to **Determine when to reduce/hedge yen exposure following **publicly observed** intervention or subsequent official disclosure.** in Japan USD/JPY, yen crosses and FX options.
## Required inputs
Legal scope, decision timestamp, intervention disclosure event × FX option tenor × quote timestamp, fields (MOF monthly/quarterly intervention releases and dates, spot FX, short-term rate differential, timestamped USDJPY options/forward data.), approved source license, trade/operating costs and untouched outcome window.
## Steps
1. Inspect SPEC H1/H0 and Distinct from multilingual monetary policy semantic shocks; targets executed FX operations and retrospective labeling bias.
2. Cite official source links, separate publication from effective date; follow MOF 2026 Q3 intervention details published Nov 9, 2026; never use ex-post intervention date labels in same-day live-time signals.
3. Build a synthetic point-in-time fixture with missing, late and contradictory events.
4. Reproduce baseline `Standard spot momentum and monetary-policy announcement dummy`, compare to do-nothing under matched constraints.
5. Prototype `Disclosure-timestamp event study with matched controls and local projections` and retain `Partial-identification causal synthetic control separating information, execution and portfolio-flow channels` only if ablation justifies.
6. Evaluate `incremental forward skew/vol forecast skill, delta-hedged net P&L, placebo events, risk-adjusted drawdown`; stress Actual intervention execution is not transparently known in real time; small event count undermines causal certainty.
7. Apply hard stop: No differential response versus rate/central-bank news controls on withheld intervention disclosures or net-option-cost results.
8. Report cost/capacity and explicit invented ROI sensitivity separately from verified empirical effects.
9. Update HANDOFF with evidence links and red flags; no live integration without human signoff.
## Output contract
Proposed `source_ledger.json`, `pit_manifest.json`, `baseline_metrics.json`, `candidate_metrics.json`, `risk_report.md`, `review_record.md` (not created by this doc PR).
## Failure behavior
Missing data rights or no feasible comparator → BLOCKED; do not fabricate a substitution, source license or outcome.
