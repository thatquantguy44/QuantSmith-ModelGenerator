# HANDOFF — Evergreen Repo Early-Termination Optionality Risk Budget
**Handoff status:** BLOCKED / design only.
**What was completed:** specification, design and reusable AI contract Markdown. **What was not completed:** code, API connectivity, license approval, source data downloads, CI, experiments, backtest, validated metrics or live deployment.
**Research owner/approvers:** not assigned.

## Next permitted milestone
Review source and copyright/usage rights for Synthetic open-repo terms, public SOFR and OFR repo curve history, legally enforceable reset/termination terms and funding costs.. Implement a synthetic event-time fixture at contract × notice period × funding day × interest-rate state, then the baseline: Static repo spread plus deterministic notice-day funding reserve.

## Blockers
1. Rights and point-in-time coverage for licensed executable repo term quotations and historical contract optionality research; approved agreement termination terms and repo open-contract events is **not** for public GitHub.
2. Legal/operational scope: Bilateral notice terms, term borrowing capacity, haircuts and closeout spreads constrain exercise decisions.
3. Identification: Non-observed counterparty exercise behavior; public term repo alone does not identify proprietary notice clauses.
4. Benefit estimates are illustrative only: $180k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 10 months; annual gross benefit scenarios $0k / $105k / $270k (downside/base/upside) for the remaining 1.1666666666666667 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -31.9% / 75.0%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Reproducibility envelope
Archive source/version/available-at fields, market session calendar, code SHA, fixed seed, input fingerprint, solver tolerances, costs, split cutoffs, unit conventions and reviewer signatures. Never include private input rows or counterparty names.

**Falsification precommitment:** Option charge unstable or no improvement over conservative notice reserve in stress holdouts.
**Distinctness:** Prior repo term-structure forecasting models *fixed-tenor spreads*; this values unilateral open-term exercise mechanics.
