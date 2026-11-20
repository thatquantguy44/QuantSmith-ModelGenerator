# HANDOFF — Noncash Collateral Correlation-Cluster Haircut Controller
**Handoff status:** BLOCKED / design only.
**What was completed:** specification, design and reusable AI contract Markdown. **What was not completed:** code, API connectivity, license approval, source data downloads, CI, experiments, backtest, validated metrics or live deployment.
**Research owner/approvers:** not assigned.

## Next permitted milestone
Review source and copyright/usage rights for Approved collateral constituents, synthetic issuer cross-holdings, stressed factor returns, liquidation bid/ask, haircut and legal threshold.. Implement a synthetic event-time fixture at collateral security × issuer cluster × loan exposure × as-of time, then the baseline: Uniform issuer/asset-class static haircut.

## Blockers
1. Rights and point-in-time coverage for licensed security-level collateral stress pricing and asset liquidity data; approved book collateral inventory and haircut agreements is **not** for public GitHub.
2. Legal/operational scope: Financing spread effects, haircuts, asset transfer restrictions, concentration penalties and market impact.
3. Identification: Asset covariance may break exactly when haircuts are needed and public free-float proxies omit liquidation controls.
4. Benefit estimates are illustrative only: $210k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 9 months; annual gross benefit scenarios $0k / $145k / $320k (downside/base/upside) for the remaining 1.25 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -13.7% / 90.5%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Reproducibility envelope
Archive source/version/available-at fields, market session calendar, code SHA, fixed seed, input fingerprint, solver tolerances, costs, split cutoffs, unit conventions and reviewer signatures. Never include private input rows or counterparty names.

**Falsification precommitment:** Risk benefit disappears when using stressed-correlation holdouts or violates legal haircut floors.
**Distinctness:** Not stale-mark quarantine (price integrity) or wrong-way *borrower default* risk: chooses collateral cluster haircut policy at portfolio level.
