# HANDOFF — Issuer Customer-Concentration Disclosure to Earnings Options Skew
**Handoff status:** BLOCKED / design only.
**What was completed:** specification, design and reusable AI contract Markdown. **What was not completed:** code, API connectivity, license approval, source data downloads, CI, experiments, backtest, validated metrics or live deployment.
**Research owner/approvers:** not assigned.

## Next permitted milestone
Review source and copyright/usage rights for SEC EDGAR original issuer filings, customer concentration disclosures, single-stock option surface, earnings calendar, liquidity and corporate actions.. Implement a synthetic event-time fixture at issuer accepted filing × reported customer share × options quote timestamp, then the baseline: Size/leverage/industry/earnings event-only option skew estimator.

## Blockers
1. Rights and point-in-time coverage for licensed historical options chain quotes, bid/ask, corporate actions and implied vols; none required initially; optional approved internal hedging fills is **not** for public GitHub.
2. Legal/operational scope: Option open interest, bid/ask, assignment/maturity mechanics and volatile event hedging friction.
3. Identification: Customer concentrations may be anonymized and nonrandomly omitted; options trade data can be illiquid.
4. Benefit estimates are illustrative only: $160k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 9 months; annual gross benefit scenarios $0k / $85k / $260k (downside/base/upside) for the remaining 1.25 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -33.6% / 103.1%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Reproducibility envelope
Archive source/version/available-at fields, market session calendar, code SHA, fixed seed, input fingerprint, solver tolerances, costs, split cutoffs, unit conventions and reviewer signatures. Never include private input rows or counterparty names.

**Falsification precommitment:** No post-filing incremental skew or hedge gain beyond conventional earnings-related jump risk.
**Distinctness:** Prior Japan buyback execution, AI capex and global factors differ from customer-dependent equity jump risk around original filings.
