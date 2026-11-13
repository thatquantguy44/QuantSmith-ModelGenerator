# ROADMAP — Synthetic Borrow Supply via Options Parity
**Week 1–2: Feasibility.** Validate source access for Options bid/ask, dividends, loan fees, stock price, funding, margin and assignment mechanics; confirm choose physical versus synthetic financing exposure, legal restrictions, unit, economics and initial research cost. Stop if licensed data, event clock or legally possible alternatives are absent.
**Week 3–4: Baseline.** Establish synthetic fixtures and a cost-inclusive `physical borrow only` simulator. Gate: AC-001/AC-002 and signed specification.
**Week 5–8: Candidate.** Prototype `implied financing via corrected put-call parity`; consider `mixed-integer derivative replication with exercise constraints` only after a controlled ablation. Gate: interpretable holdout comparison and no future information.
**Week 9–12: Shadow review.** Present `executable financing benefit, hedge error, margin and basis risk`, confidence ranges, incident/risk scenarios and break-even costs. Stop if advantage does not survive costs or American exercise and forecast-dividend mismatch.
**Beyond:** Human approval before any real data connection or live integration. No deployment is implied.
