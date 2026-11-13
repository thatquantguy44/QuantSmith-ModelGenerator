# ROADMAP — Financing Execution Shortfall Model
**Week 1–2: Feasibility.** Validate source access for Timestamped RFQs, quotes, fill/rejects, booked fees, market moves and settlement; confirm diagnose where quoted financing economics leak before completed settlement, legal restrictions, unit, economics and initial research cost. Stop if licensed data, event clock or legally possible alternatives are absent.
**Week 3–4: Baseline.** Establish synthetic fixtures and a cost-inclusive `executed spread minus indicative quote` simulator. Gate: AC-001/AC-002 and signed specification.
**Week 5–8: Candidate.** Prototype `cost-inclusive execution shortfall event ledger`; consider `matched counterfactual execution-policy evaluator` only after a controlled ablation. Gate: interpretable holdout comparison and no future information.
**Week 9–12: Shadow review.** Present `bps slippage, recovered P&L, latency and fill rate`, confidence ranges, incident/risk scenarios and break-even costs. Stop if advantage does not survive costs or quotes may be non-executable; client selection creates bias.
**Beyond:** Human approval before any real data connection or live integration. No deployment is implied.
