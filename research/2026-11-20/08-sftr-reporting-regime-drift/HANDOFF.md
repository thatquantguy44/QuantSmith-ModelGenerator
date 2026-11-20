# HANDOFF — SFTR Reporting Regime Drift and Public-Private Divergence Detector
**Handoff status:** BLOCKED / design only.
**What was completed:** specification, design and reusable AI contract Markdown. **What was not completed:** code, API connectivity, license approval, source data downloads, CI, experiments, backtest, validated metrics or live deployment.
**Research owner/approvers:** not assigned.

## Next permitted milestone
Review source and copyright/usage rights for ESMA reporting rules and publications, public aggregate exposures where available, historical methodology changes, synthetic backdated schema versions.. Implement a synthetic event-time fixture at SFTR public aggregate series × jurisdiction × report vintage, then the baseline: Fixed ±3-sigma z-score alert on each series.

## Blockers
1. Rights and point-in-time coverage for licensed vendor-assembled SFTR regulatory trend panels; approved trade repository access strictly subject to supervisory entitlements is **not** for public GitHub.
2. Legal/operational scope: Low runtime; review cost per alert and regulator/source availability dominate feasibility.
3. Identification: Only public aggregate data may be available, making root-cause verification incomplete.
4. Benefit estimates are illustrative only: $135k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 6 months; annual gross benefit scenarios $0k / $90k / $190k (downside/base/upside) for the remaining 1.5 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / 0.0% / 111.1%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Reproducibility envelope
Archive source/version/available-at fields, market session calendar, code SHA, fixed seed, input fingerprint, solver tolerances, costs, split cutoffs, unit conventions and reviewer signatures. Never include private input rows or counterparty names.

**Falsification precommitment:** Synthetic change fixtures not detected within agreed delay or false alerts exceed preregistered burden.
**Distinctness:** Prior identity reconciliation matches transactions across books; this detects public reporting *regime and taxonomy changes*.
