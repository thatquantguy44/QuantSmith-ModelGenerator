# HANDOFF — Asia–US Cross-Listed ADR Opening Auction Information Transfer
**Handoff status:** BLOCKED / design only.
**What was completed:** specification, design and reusable AI contract Markdown. **What was not completed:** code, API connectivity, license approval, source data downloads, CI, experiments, backtest, validated metrics or live deployment.
**Research owner/approvers:** not assigned.

## Next permitted milestone
Review source and copyright/usage rights for Issuer depositary receipts ratios, local listings, public filings, FX quote timestamps, US ADR opening auctions, dividends and corporate action history.. Implement a synthetic event-time fixture at ADR × home-market session × US opening-auction timestamp, then the baseline: Last home close × publicly known ADR conversion ratio × contemporaneous FX spot.

## Blockers
1. Rights and point-in-time coverage for licensed US ADR and Asia local shares auction quotes, intraday FX, depositary ratio history; optional approved order-level fills for execution validation is **not** for public GitHub.
2. Legal/operational scope: ADR opening auction depth, ADR conversion channel capacity, local/US holiday and FX hedging constraints.
3. Identification: ADR conversion fees, access restrictions, local holidays and stale home quotes create phantom arbitrage.
4. Benefit estimates are illustrative only: $225k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 10 months; annual gross benefit scenarios $0k / $120k / $310k (downside/base/upside) for the remaining 1.1666666666666667 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -37.8% / 60.7%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Reproducibility envelope
Archive source/version/available-at fields, market session calendar, code SHA, fixed seed, input fingerprint, solver tolerances, costs, split cutoffs, unit conventions and reviewer signatures. Never include private input rows or counterparty names.

**Falsification precommitment:** No consistent opening execution improvement after financing, foreign exchange, depositary and auction spread costs.
**Distinctness:** Prior global covariance regime and FX hedge programs forecast portfolio risk; this models cross-listed single-name auction lead-lag with depositary mechanics.
