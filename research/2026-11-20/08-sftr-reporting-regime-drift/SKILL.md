---
name: sftr-reporting-regime-drift
description: "Reusable research skill for SFTR Reporting Regime Drift and Public-Private Divergence Detector; source-time-aware falsifiable economic evaluation. No live trading."
---
# Research skill — SFTR Reporting Regime Drift and Public-Private Divergence Detector
## Trigger
When a quant team asks to **Detect structural reporting-quality breaks before using reported SFTR aggregates as market exposure signals.** in European securities financing transaction repositories.
## Required inputs
Legal scope, decision timestamp, SFTR public aggregate series × jurisdiction × report vintage, fields (ESMA reporting rules and publications, public aggregate exposures where available, historical methodology changes, synthetic backdated schema versions.), approved source license, trade/operating costs and untouched outcome window.
## Steps
1. Inspect SPEC H1/H0 and Prior identity reconciliation matches transactions across books; this detects public reporting *regime and taxonomy changes*.
2. Cite official source links, separate publication from effective date; follow Use publication timestamps and repository versions, not reporting reference dates; detailed transaction data are supervisor-restricted.
3. Build a synthetic point-in-time fixture with missing, late and contradictory events.
4. Reproduce baseline `Fixed ±3-sigma z-score alert on each series`, compare to do-nothing under matched constraints.
5. Prototype `Robust multivariate Bayesian online change-point detection` and retain `Hierarchical regime/missingness change-point models with document version embeddings as covariates` only if ablation justifies.
6. Evaluate `break detection delay, false alarms, post-correction economic interpretation stability`; stress Only public aggregate data may be available, making root-cause verification incomplete.
7. Apply hard stop: Synthetic change fixtures not detected within agreed delay or false alerts exceed preregistered burden.
8. Report cost/capacity and explicit invented ROI sensitivity separately from verified empirical effects.
9. Update HANDOFF with evidence links and red flags; no live integration without human signoff.
## Output contract
Proposed `source_ledger.json`, `pit_manifest.json`, `baseline_metrics.json`, `candidate_metrics.json`, `risk_report.md`, `review_record.md` (not created by this doc PR).
## Failure behavior
Missing data rights or no feasible comparator → BLOCKED; do not fabricate a substitution, source license or outcome.
