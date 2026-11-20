---
name: evergreen-repo-termination-option
description: "Reusable research skill for Evergreen Repo Early-Termination Optionality Risk Budget; source-time-aware falsifiable economic evaluation. No live trading."
---
# Research skill — Evergreen Repo Early-Termination Optionality Risk Budget
## Trigger
When a quant team asks to **Set rate/tenor risk charges for unilateral termination and extension rights in open repo or evergreen funding.** in Open and evergreen secured funding agreements.
## Required inputs
Legal scope, decision timestamp, contract × notice period × funding day × interest-rate state, fields (Synthetic open-repo terms, public SOFR and OFR repo curve history, legally enforceable reset/termination terms and funding costs.), approved source license, trade/operating costs and untouched outcome window.
## Steps
1. Inspect SPEC H1/H0 and Prior repo term-structure forecasting models *fixed-tenor spreads*; this values unilateral open-term exercise mechanics.
2. Cite official source links, separate publication from effective date; follow Public repo rates have release lags; exact contract termination rights must be known at contract initiation, not retrofitted.
3. Build a synthetic point-in-time fixture with missing, late and contradictory events.
4. Reproduce baseline `Static repo spread plus deterministic notice-day funding reserve`, compare to do-nothing under matched constraints.
5. Prototype `Least-squares Monte Carlo for bilateral asymmetric stop decisions` and retain `Nonzero-sum stochastic game with liquidity-dependent termination intensities` only if ablation justifies.
6. Evaluate `replacement funding loss, option premium calibration, cash-flow stress, tail liquidity gap`; stress Non-observed counterparty exercise behavior; public term repo alone does not identify proprietary notice clauses.
7. Apply hard stop: Option charge unstable or no improvement over conservative notice reserve in stress holdouts.
8. Report cost/capacity and explicit invented ROI sensitivity separately from verified empirical effects.
9. Update HANDOFF with evidence links and red flags; no live integration without human signoff.
## Output contract
Proposed `source_ledger.json`, `pit_manifest.json`, `baseline_metrics.json`, `candidate_metrics.json`, `risk_report.md`, `review_record.md` (not created by this doc PR).
## Failure behavior
Missing data rights or no feasible comparator → BLOCKED; do not fabricate a substitution, source license or outcome.
