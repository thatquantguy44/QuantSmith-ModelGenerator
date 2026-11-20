---
name: eu-csdr-penalty-queue-policy
description: "Reusable research skill for European CSDR Penalty-Aware Settlement Queue Prioritization; source-time-aware falsifiable economic evaluation. No live trading."
---
# Research skill — European CSDR Penalty-Aware Settlement Queue Prioritization
## Trigger
When a quant team asks to **Prioritize settlement instructions under explicit penalty eligibility and scarce processing resources.** in EU CSD securities settlement / securities finance return legs.
## Required inputs
Legal scope, decision timestamp, instruction × CSD × ISIN × intended settlement day × decision time, fields (Public ESMA CSDR framework, synthetic ISIN liquidity/penalty groups, settlement instruction cutoff, fail reason and amendment history.), approved source license, trade/operating costs and untouched outcome window.
## Steps
1. Inspect SPEC H1/H0 and Differs from past buy-in-vs-wait timing and settlement contagion: this chooses *ex-ante* multi-instruction processing order under cash penalty rules.
2. Cite official source links, separate publication from effective date; follow Penalty exclusions and rules must reflect versions legally in force before each instruction decision; ESMA technical advice is not automatically operative law.
3. Build a synthetic point-in-time fixture with missing, late and contradictory events.
4. Reproduce baseline `FIFO or largest-notional-first allowed settlement priority`, compare to do-nothing under matched constraints.
5. Prototype `Constrained weighted-shortest-processing-time queue policy with eligibility rules` and retain `Approximate dynamic programming under stochastic matched delivery arrival times` only if ablation justifies.
6. Evaluate `penalty liability, fail-days, priority-rule violations, operational throughput`; stress Misclassification of non-attributable fail causes or legal exclusion yields incorrect optimized queues.
7. Apply hard stop: No statistically measurable improvement in held-out synthetic and later approved settlement scenarios under equal capacity.
8. Report cost/capacity and explicit invented ROI sensitivity separately from verified empirical effects.
9. Update HANDOFF with evidence links and red flags; no live integration without human signoff.
## Output contract
Proposed `source_ledger.json`, `pit_manifest.json`, `baseline_metrics.json`, `candidate_metrics.json`, `risk_report.md`, `review_record.md` (not created by this doc PR).
## Failure behavior
Missing data rights or no feasible comparator → BLOCKED; do not fabricate a substitution, source license or outcome.
