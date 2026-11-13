# ROADMAP — Cleared Versus Tri-Party Repo Fragmentation Nowcast
## Stage 0 — evidence feasibility (weeks 1–2)
- Validate public data meaning, historical vintages, publication lag and any commercial license for **United States short-term funding markets**.
- Confirm action/market legal constraints, unit conventions and venue × collateral class × tenor × underlying observation date, plus public publication timestamp.
- Gate: stop if input authorization, comparable baseline or event-time record is unavailable.

## Stage 1 — reproducible baseline (weeks 3–4)
- Create synthetic event fixtures with adverse missing/revision scenarios.
- Implement SOFR level change and aggregate funding volume z-score. and hard feasibility tests.
- Gate: AC-001, AC-002, AC-005.

## Stage 2 — candidate science (weeks 5–8)
- Implement State-space latent fragmentation index with lag-aware missingness., compare matched chronological holdouts, audit Revised/missing suppressed OFR cells and cross-venue holiday timing can create lookahead and artificial divergences..
- Consider Hierarchical online change-point and causal regime attribution by venue and reporting channel. only on preregistered incremental value.
- Gate: Reject if lag-safe AUPRC does not exceed SOFR-only benchmark by 0.03 on an untouched crisis/quiet holdout.

## Stage 3 — controlled shadow evaluation (weeks 9–12)
- Measure next-session stress AUPRC, calibrated Brier score, false alarm rate, funding stress drawdown., the relevant capacity constraints and all-in implementation cost.
- Replace illustrative 24-month ROI (-68% to 68%) with source-backed measured economics or explicitly retain uncertainty.
- Gate: independent risk/compliance review, adequate tail robustness, reproducibility evidence.

## Deferred production
Requires separate feature PR, CI, audit controls, monitoring, rollback and human authorization. No live trading or private data is authorized by this package.
