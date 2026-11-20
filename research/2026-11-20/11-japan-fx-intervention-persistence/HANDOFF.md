# HANDOFF — Japan FX Intervention Impact and Option-Skew Persistence
**Handoff status:** BLOCKED / design only.
**What was completed:** specification, design and reusable AI contract Markdown. **What was not completed:** code, API connectivity, license approval, source data downloads, CI, experiments, backtest, validated metrics or live deployment.
**Research owner/approvers:** not assigned.

## Next permitted milestone
Review source and copyright/usage rights for MOF monthly/quarterly intervention releases and dates, spot FX, short-term rate differential, timestamped USDJPY options/forward data.. Implement a synthetic event-time fixture at intervention disclosure event × FX option tenor × quote timestamp, then the baseline: Standard spot momentum and monetary-policy announcement dummy.

## Blockers
1. Rights and point-in-time coverage for licensed timestamped USDJPY spot/option vols and historical intervention newswire alerts; permissioned dealer FX order-flow data (optional; exclude from public repo) is **not** for public GitHub.
2. Legal/operational scope: Executable FX spot/options spreads, liquidity, event jump exposure, market access and derivatives capital.
3. Identification: Actual intervention execution is not transparently known in real time; small event count undermines causal certainty.
4. Benefit estimates are illustrative only: $180k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 8 months; annual gross benefit scenarios $0k / $95k / $240k (downside/base/upside) for the remaining 1.3333333333333333 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -29.6% / 77.8%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Reproducibility envelope
Archive source/version/available-at fields, market session calendar, code SHA, fixed seed, input fingerprint, solver tolerances, costs, split cutoffs, unit conventions and reviewer signatures. Never include private input rows or counterparty names.

**Falsification precommitment:** No differential response versus rate/central-bank news controls on withheld intervention disclosures or net-option-cost results.
**Distinctness:** Distinct from multilingual monetary policy semantic shocks; targets executed FX operations and retrospective labeling bias.
