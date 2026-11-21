# HANDOFF — EU ETS Auction Supply Revision and Carbon Futures Carry
**Handoff status:** BLOCKED / design only.
**What was completed:** specification, design and reusable AI contract Markdown. **What was not completed:** code, API connectivity, license approval, source data downloads, CI, experiments, backtest, validated metrics or live deployment.
**Research owner/approvers:** not assigned.

## Next permitted milestone
Review source and copyright/usage rights for European Commission vintage auction calendars, Union Registry verified emissions/compliance, dated policy changes, EUA/power/gas contract prices.. Implement a synthetic event-time fixture at EU ETS auction calendar publication × allowance futures tenor × exchange quote timestamp, then the baseline: Calendar-month fixed seasonal allowance spread.

## Blockers
1. Rights and point-in-time coverage for licensed EEX/ICE carbon futures curves and executable bid/ask; approved utility compliance balances and hedge exposures only in private setting is **not** for public GitHub.
2. Legal/operational scope: EUA contract liquidity, expiry rolling, carbon compliance mandates and margin/collateral limits.
3. Identification: Policy revision expectations may be priced before official publication; futures/Registry coverage not contemporaneous.
4. Benefit estimates are illustrative only: $210k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 9 months; annual gross benefit scenarios $0k / $125k / $310k (downside/base/upside) for the remaining 1.25 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -25.6% / 84.5%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Reproducibility envelope
Archive source/version/available-at fields, market session calendar, code SHA, fixed seed, input fingerprint, solver tolerances, costs, split cutoffs, unit conventions and reviewer signatures. Never include private input rows or counterparty names.

**Falsification precommitment:** No out-of-sample spread forecast or hedge benefit net of spreads after matched energy factors.
**Distinctness:** Not prior European gas storage deliverability; models ETS allowance auction policy supply and carbon forward carry.
