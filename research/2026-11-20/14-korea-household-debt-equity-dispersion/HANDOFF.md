# HANDOFF — Korean Household Debt-Service Shock to Bank–Consumer Equity Spread
**Handoff status:** BLOCKED / design only.
**What was completed:** specification, design and reusable AI contract Markdown. **What was not completed:** code, API connectivity, license approval, source data downloads, CI, experiments, backtest, validated metrics or live deployment.
**Research owner/approvers:** not assigned.

## Next permitted milestone
Review source and copyright/usage rights for BIS Korea household DSR, BOK/Statistics Korea public lending/rates, issuer earnings and local equity returns, reporting vintage.. Implement a synthetic event-time fixture at quarterly DSR release × issuer × accounting period × price timestamp, then the baseline: Equal-beta long banks short consumer discretionary with lagged policy-rate signal.

## Blockers
1. Rights and point-in-time coverage for licensed historical KOSPI sector fundamentals, point-in-time prices and analyst revisions; optional private investor positioning and execution model, not required for initial study is **not** for public GitHub.
2. Legal/operational scope: Local borrow, FX hedge, Korean market access, corporate action history, sector liquidity and taxes.
3. Identification: Endogenous rate policy and sector composition cause confounding; public issuer histories need delisting continuity.
4. Benefit estimates are illustrative only: $170k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 9 months; annual gross benefit scenarios $0k / $105k / $260k (downside/base/upside) for the remaining 1.25 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -22.8% / 91.2%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Reproducibility envelope
Archive source/version/available-at fields, market session calendar, code SHA, fixed seed, input fingerprint, solver tolerances, costs, split cutoffs, unit conventions and reviewer signatures. Never include private input rows or counterparty names.

**Falsification precommitment:** No stable expected-earnings or beta-neutral sector difference once rates and economy factors are controlled.
**Distinctness:** Distinct from EM external debt currency mismatch and South Africa power reliability; Korean domestic household burden drives cross-sector equity dispersion.
