# HANDOFF — Canadian Mortgage Renewal Cohorts to Bank Credit-Risk Dispersion
**Handoff status:** BLOCKED / design only.
**What was completed:** specification, design and reusable AI contract Markdown. **What was not completed:** code, API connectivity, license approval, source data downloads, CI, experiments, backtest, validated metrics or live deployment.
**Research owner/approvers:** not assigned.

## Next permitted milestone
Review source and copyright/usage rights for Bank of Canada public mortgage balances/rates, staff renewal methodology, bank annual/quarterly mortgage disclosures, CAD rate and housing data.. Implement a synthetic event-time fixture at Canadian mortgage cohort × monthly public release × bank quarterly filing, then the baseline: Bank loss sensitivity to national unemployment and policy rate alone.

## Blockers
1. Rights and point-in-time coverage for licensed Canadian bank CDS/price, historical mortgage cohort distribution data; optional bank-level loan data only by approved legal agreements is **not** for public GitHub.
2. Legal/operational scope: TSX bank/equity/CDS liquidity, CAD FX basis, sector beta hedges and credit market impact.
3. Identification: Public aggregate cohorts do not identify each bank's borrower vintage distribution or underwriting quality.
4. Benefit estimates are illustrative only: $160k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 8 months; annual gross benefit scenarios $0k / $105k / $240k (downside/base/upside) for the remaining 1.3333333333333333 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -12.5% / 100.0%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Reproducibility envelope
Archive source/version/available-at fields, market session calendar, code SHA, fixed seed, input fingerprint, solver tolerances, costs, split cutoffs, unit conventions and reviewer signatures. Never include private input rows or counterparty names.

**Falsification precommitment:** No cross-bank predictive signal after public loan books and unemployment/rate controls, or estimates too wide to act on.
**Distinctness:** Compared with Korean household DSR, this is Canadian *mortgage fixed-rate renewal cohort repricing* versus bank credit loss forecasts.
