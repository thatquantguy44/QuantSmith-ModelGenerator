# HANDOFF — European CSDR Penalty-Aware Settlement Queue Prioritization
**Handoff status:** BLOCKED / design only.
**What was completed:** specification, design and reusable AI contract Markdown. **What was not completed:** code, API connectivity, license approval, source data downloads, CI, experiments, backtest, validated metrics or live deployment.
**Research owner/approvers:** not assigned.

## Next permitted milestone
Review source and copyright/usage rights for Public ESMA CSDR framework, synthetic ISIN liquidity/penalty groups, settlement instruction cutoff, fail reason and amendment history.. Implement a synthetic event-time fixture at instruction × CSD × ISIN × intended settlement day × decision time, then the baseline: FIFO or largest-notional-first allowed settlement priority.

## Blockers
1. Rights and point-in-time coverage for licensed CSD settlement penalty rate and instruction history datasets; authorized ISIN-level fail reason, settlement queues and participant obligations is **not** for public GitHub.
2. Legal/operational scope: Settlement bandwidth/available inventory and mandatory processing priority; adverse-penalty reallocations cannot violate service commitments.
3. Identification: Misclassification of non-attributable fail causes or legal exclusion yields incorrect optimized queues.
4. Benefit estimates are illustrative only: $145k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 7 months; annual gross benefit scenarios $0k / $100k / $250k (downside/base/upside) for the remaining 1.4166666666666667 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -2.3% / 144.3%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Reproducibility envelope
Archive source/version/available-at fields, market session calendar, code SHA, fixed seed, input fingerprint, solver tolerances, costs, split cutoffs, unit conventions and reviewer signatures. Never include private input rows or counterparty names.

**Falsification precommitment:** No statistically measurable improvement in held-out synthetic and later approved settlement scenarios under equal capacity.
**Distinctness:** Differs from past buy-in-vs-wait timing and settlement contagion: this chooses *ex-ante* multi-instruction processing order under cash penalty rules.
