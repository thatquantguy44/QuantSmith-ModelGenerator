---
name: korea-household-debt-equity-dispersion
description: "Reusable research skill for Korean Household Debt-Service Shock to Bank–Consumer Equity Spread; source-time-aware falsifiable economic evaluation. No live trading."
---
# Research skill — Korean Household Debt-Service Shock to Bank–Consumer Equity Spread
## Trigger
When a quant team asks to **Hedge relative exposure of Korean bank and consumer equities across household debt-service regime changes.** in South Korea household credit, KOSPI/KOSDAQ banks and consumer discretionary.
## Required inputs
Legal scope, decision timestamp, quarterly DSR release × issuer × accounting period × price timestamp, fields (BIS Korea household DSR, BOK/Statistics Korea public lending/rates, issuer earnings and local equity returns, reporting vintage.), approved source license, trade/operating costs and untouched outcome window.
## Steps
1. Inspect SPEC H1/H0 and Distinct from EM external debt currency mismatch and South Africa power reliability; Korean domestic household burden drives cross-sector equity dispersion.
2. Cite official source links, separate publication from effective date; follow BIS Korean DSR published with quarterly lag (available through 2026-Q1 on checked dataset page); do not trade on 2026-Q2 unless publicly released.
3. Build a synthetic point-in-time fixture with missing, late and contradictory events.
4. Reproduce baseline `Equal-beta long banks short consumer discretionary with lagged policy-rate signal`, compare to do-nothing under matched constraints.
5. Prototype `Panel local projections with shrinkage and sector time fixed effects` and retain `Dynamic heterogeneous household credit impulse response with instrumented policy-rate shocks` only if ablation justifies.
6. Evaluate `cross-sector earnings forecast delta, beta-neutral IR, worst-regime drawdown, capacity after local spreads`; stress Endogenous rate policy and sector composition cause confounding; public issuer histories need delisting continuity.
7. Apply hard stop: No stable expected-earnings or beta-neutral sector difference once rates and economy factors are controlled.
8. Report cost/capacity and explicit invented ROI sensitivity separately from verified empirical effects.
9. Update HANDOFF with evidence links and red flags; no live integration without human signoff.
## Output contract
Proposed `source_ledger.json`, `pit_manifest.json`, `baseline_metrics.json`, `candidate_metrics.json`, `risk_report.md`, `review_record.md` (not created by this doc PR).
## Failure behavior
Missing data rights or no feasible comparator → BLOCKED; do not fabricate a substitution, source license or outcome.
