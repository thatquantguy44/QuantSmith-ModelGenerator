# HANDOFF — US TIPS CPI Indexation-Lag Carry and Breakeven Calendar Surface
**Handoff status:** BLOCKED / design only.
**What was completed:** specification, design and reusable AI contract Markdown. **What was not completed:** code, API connectivity, license approval, source data downloads, CI, experiments, backtest, validated metrics or live deployment.
**Research owner/approvers:** not assigned.

## Next permitted milestone
Review source and copyright/usage rights for Treasury official daily TIPS index ratios/CPI, vintage BLS CPI, nominal/TIPS quotes, issue terms, accrued interest.. Implement a synthetic event-time fixture at TIPS CUSIP × CPI/index-ratio effective date × decision timestamp, then the baseline: Duration-matched TIPS-minus-nominal bond without CPI-calendar signal.

## Blockers
1. Rights and point-in-time coverage for licensed nominal/TIPS bond transaction and inflation swap market data; optional approved portfolio duration and executed bond quotes is **not** for public GitHub.
2. Legal/operational scope: Issue-level depth, coupon accrued interest, repo funding, bid-ask, tax and duration hedging constraints.
3. Identification: Illiquid issue quotations, inflation floor optionality, unrevised CPI data and seasonality overfit.
4. Benefit estimates are illustrative only: $135k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 6 months; annual gross benefit scenarios $0k / $105k / $200k (downside/base/upside) for the remaining 1.5 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / 16.7% / 122.2%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Reproducibility envelope
Archive source/version/available-at fields, market session calendar, code SHA, fixed seed, input fingerprint, solver tolerances, costs, split cutoffs, unit conventions and reviewer signatures. Never include private input rows or counterparty names.

**Falsification precommitment:** Improvement vanishes versus a carry-only and time-matched duration hedge after execution spread costs.
**Distinctness:** Prior US-Euro sovereign curve shock model decomposes release shocks; this prices U.S. issue-specific TIPS CPI indexation carry.
