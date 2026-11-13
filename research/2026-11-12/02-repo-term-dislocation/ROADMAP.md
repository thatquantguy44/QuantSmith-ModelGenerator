# ROADMAP — Repo Term Structure Dislocation Engine
**Week 1–2: Feasibility.** Validate source access for Repo rate/tenor quotes, SOFR, collateral CUSIP, haircut, balance-sheet dates; confirm choose term financing maturity and collateral route, legal restrictions, unit, economics and initial research cost. Stop if licensed data, event clock or legally possible alternatives are absent.
**Week 3–4: Baseline.** Establish synthetic fixtures and a cost-inclusive `overnight funding rollover` simulator. Gate: AC-001/AC-002 and signed specification.
**Week 5–8: Candidate.** Prototype `security-aware no-arbitrage term curve`; consider `regime-switching state-space financing optimization` only after a controlled ablation. Gate: interpretable holdout comparison and no future information.
**Week 9–12: Shadow review.** Present `after-cost funding savings, basis convergence, risk and drawdown`, confidence ranges, incident/risk scenarios and break-even costs. Stop if advantage does not survive costs or indicative prices and bid/ask execution mismatch.
**Beyond:** Human approval before any real data connection or live integration. No deployment is implied.
