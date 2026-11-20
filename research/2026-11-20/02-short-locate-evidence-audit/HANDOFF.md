# HANDOFF — Reg SHO Locate Evidence and Borrow-Capacity Audit Engine
**Handoff status:** BLOCKED / design only.
**What was completed:** specification, design and reusable AI contract Markdown. **What was not completed:** code, API connectivity, license approval, source data downloads, CI, experiments, backtest, validated metrics or live deployment.
**Research owner/approvers:** not assigned.

## Next permitted milestone
Review source and copyright/usage rights for Synthetic short-sale order events, documented locate timestamps, source identity, shares remaining, exemptions and post-trade recalls; later private desk records only if approved.. Implement a synthetic event-time fixture at short-sale request × account × security × source × event timestamp, then the baseline: End-of-day deterministic locate exception SQL rules.

## Blockers
1. Rights and point-in-time coverage for audited market locate reference data where licensed; broker order/locate logs only in approved production compliance environment is **not** for public GitHub.
2. Legal/operational scope: Low per-request CPU; overhead per manual escalation and strict audit storage/retention authorization.
3. Identification: Reg SHO exemptions, broker responsibilities and settlement rules require qualified legal interpretation.
4. Benefit estimates are illustrative only: $120k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 6 months; annual gross benefit scenarios $0k / $115k / $200k (downside/base/upside) for the remaining 1.5 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / 43.8% / 150.0%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Reproducibility envelope
Archive source/version/available-at fields, market session calendar, code SHA, fixed seed, input fingerprint, solver tolerances, costs, split cutoffs, unit conventions and reviewer signatures. Never include private input rows or counterparty names.

**Falsification precommitment:** Fails to flag intentionally missing/expired/overused locates on synthetic fixtures or blocks materially more valid trades than comparator.
**Distinctness:** Unlike old loan-fee selection correction, tests documentation/quantity compliance and audit proof, not fair value or pricing.
