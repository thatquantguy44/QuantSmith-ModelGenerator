# HANDOFF — ETF Creation/Redemption Basket Shock to Stock-Loan Supply
**Handoff status:** BLOCKED / design only.
**What was completed:** specification, design and reusable AI contract Markdown. **What was not completed:** code, API connectivity, license approval, source data downloads, CI, experiments, backtest, validated metrics or live deployment.
**Research owner/approvers:** not assigned.

## Next permitted milestone
Review source and copyright/usage rights for ETF disclosed holdings and creation units, public filings, official membership events, licensed AP basket/flows and loan availability for later study.. Implement a synthetic event-time fixture at ETF × constituent × creation/redemption day × publication time, then the baseline: Change in ETF shares outstanding plus index-event dummy.

## Blockers
1. Rights and point-in-time coverage for licensed NSCC/ETF basket files, creation/redemption flows and securities lending availability; permissioned lendable supply, client inventory rules and loan booking logs is **not** for public GitHub.
2. Legal/operational scope: Inventory is limited by mandate, lendability and recalls; transaction fees and timing dominate thin basket effects.
3. Identification: Most executable AP basket details and actual stock-loan supply are not public.
4. Benefit estimates are illustrative only: $190k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 9 months; annual gross benefit scenarios $0k / $130k / $280k (downside/base/upside) for the remaining 1.25 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -14.5% / 84.2%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Reproducibility envelope
Archive source/version/available-at fields, market session calendar, code SHA, fixed seed, input fingerprint, solver tolerances, costs, split cutoffs, unit conventions and reviewer signatures. Never include private input rows or counterparty names.

**Falsification precommitment:** No incremental held-out inventory signal after availability alignment and underlying stock flow controls.
**Distinctness:** Distinct from synthetic borrow put-call parity and owner's co-withdrawal risk; identifies ETF primary basket supply as separate driver.
