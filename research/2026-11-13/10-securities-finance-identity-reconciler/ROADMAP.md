# ROADMAP — Cross-Book Securities Finance Identity Reconciliation Graph
## Stage 0 — evidence feasibility (weeks 1–2)
- Validate public data meaning, historical vintages, publication lag and any commercial license for **US and cross-border securities-finance operations**.
- Confirm action/market legal constraints, unit conventions and source record × canonical candidate × event version × timestamp.
- Gate: stop if input authorization, comparable baseline or event-time record is unavailable.

## Stage 1 — reproducible baseline (weeks 3–4)
- Create synthetic event fixtures with adverse missing/revision scenarios.
- Implement Exact ID join plus manually triaged fuzzy-name matches. and hard feasibility tests.
- Gate: AC-001, AC-002, AC-005.

## Stage 2 — candidate science (weeks 5–8)
- Implement Bipartite deterministic matching with hard identity constraints and provenance., compare matched chronological holdouts, audit LLM or probabilistic model can silently merge legally distinct entities or settlement legs..
- Consider Human-review active-learning on uncertain clusters with error budget and privacy-preserving synthetic tests. only on preregistered incremental value.
- Gate: Reject if critical false merges exceed zero in labeled holdouts or operations time does not decline.

## Stage 3 — controlled shadow evaluation (weeks 9–12)
- Measure false merge rate, unmatched %, time to resolve, duplicate exposure USD, manual review hours., the relevant capacity constraints and all-in implementation cost.
- Replace illustrative 24-month ROI (-59% to 103%) with source-backed measured economics or explicitly retain uncertainty.
- Gate: independent risk/compliance review, adequate tail robustness, reproducibility evidence.

## Deferred production
Requires separate feature PR, CI, audit controls, monitoring, rollback and human authorization. No live trading or private data is authorized by this package.
