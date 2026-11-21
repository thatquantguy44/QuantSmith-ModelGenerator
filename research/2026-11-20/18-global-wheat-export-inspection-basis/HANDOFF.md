# HANDOFF — Wheat Export Inspection Revisions to Global Basis and Calendar Spreads
**Handoff status:** BLOCKED / design only.
**What was completed:** specification, design and reusable AI contract Markdown. **What was not completed:** code, API connectivity, license approval, source data downloads, CI, experiments, backtest, validated metrics or live deployment.
**Research owner/approvers:** not assigned.

## Next permitted milestone
Review source and copyright/usage rights for USDA AMS export grain inspections dashboard, USDA wheat supply/price tables, official crop calendars, futures curves and export policy announcement records.. Implement a synthetic event-time fixture at weekly USDA inspection release × grain class × destination × exchange quote timestamp, then the baseline: Monthly seasonal wheat spread regression using last known WASDE.

## Blockers
1. Rights and point-in-time coverage for licensed Black Sea export flow, futures L2 and physical basis transaction data; optional private grain merchandising data only with explicit rights is **not** for public GitHub.
2. Legal/operational scope: CME wheat futures tick, spread roll, physical basis accessibility and region transport costs.
3. Identification: Weekly inspections differ from actual export commitments; Black Sea supply and policy announcements may dominate.
4. Benefit estimates are illustrative only: $175k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 9 months; annual gross benefit scenarios $0k / $100k / $265k (downside/base/upside) for the remaining 1.25 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -28.6% / 89.3%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Reproducibility envelope
Archive source/version/available-at fields, market session calendar, code SHA, fixed seed, input fingerprint, solver tolerances, costs, split cutoffs, unit conventions and reviewer signatures. Never include private input rows or counterparty names.

**Falsification precommitment:** No predictive improvement after weather, futures calendar effects and contemporaneous official release lags.
**Distinctness:** Unlike Australian water allocation/crop basis, uses multinational export timing, inspection vintages and wheat calendar spreads.
