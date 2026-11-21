# HANDOFF — Public BDC Portfolio Fair-Value Markdown Lead Indicator
**Handoff status:** BLOCKED / design only.
**What was completed:** specification, design and reusable AI contract Markdown. **What was not completed:** code, API connectivity, license approval, source data downloads, CI, experiments, backtest, validated metrics or live deployment.
**Research owner/approvers:** not assigned.

## Next permitted milestone
Review source and copyright/usage rights for Original SEC BDC 10-Q/10-K investment schedules and mark values, sector classification, publicly known credit outcomes and licensed leveraged-loan pricing.. Implement a synthetic event-time fixture at BDC filing × portfolio company/sector × disclosure timestamp, then the baseline: BDC aggregate NAV discount and published nonaccrual percentage.

## Blockers
1. Rights and point-in-time coverage for licensed private-credit / loan issuer reference and market valuation panel; none required for initial public filings; internal credit committee notes prohibited here is **not** for public GitHub.
2. Legal/operational scope: BDC equity market depth, credit hedging basis, optional loan trading access and stale valuation discounts.
3. Identification: BDC portfolio company identities, valuation methods and distressed sales are not uniformly disclosed; matching bias.
4. Benefit estimates are illustrative only: $190k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 10 months; annual gross benefit scenarios $0k / $115k / $275k (downside/base/upside) for the remaining 1.1666666666666667 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -29.4% / 68.9%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Reproducibility envelope
Archive source/version/available-at fields, market session calendar, code SHA, fixed seed, input fingerprint, solver tolerances, costs, split cutoffs, unit conventions and reviewer signatures. Never include private input rows or counterparty names.

**Falsification precommitment:** No improvement over current NAV discount/nonaccrual baseline in later quarters or effects only known after financial reports.
**Distinctness:** Distinct from CMBS maturity/refinance hazard and TRACE ETF NAV stress: tests *BDC marked private loan holdings*.
