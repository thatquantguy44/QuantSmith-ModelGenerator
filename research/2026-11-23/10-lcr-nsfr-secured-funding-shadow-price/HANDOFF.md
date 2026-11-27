# HANDOFF — Regulatory LCR/NSFR Shadow Cost of Secured Funding Collateral
**Status:** research design delivered, **all empirical and executable work BLOCKED/not started**. Owner, legal reviewer and dataset approver: not assigned.

## Transfer to implementing researcher
**Economic decision:** Allocate financing transactions by incremental liquidity-ratio headroom consumption, not only nominal repo spread.
**Falsifiable claim:** Dual-priced LCR/NSFR constraints reorder feasible funding selections and improve all-in liquidity-adjusted economics versus spread ranking.
**First deliverable:** synthetic/point-in-time fixture and reproducible `Rank repo offers by quoted rate subject to gross notional limits`.
**Then:** Linear/mixed-integer secured funding allocation with LCR/NSFR dual-price attribution.
**Stop:** No cost difference over conservative liquidity-constrained benchmark or unstable/uninterpretable duals..

## Required unresolved inputs
- Licence and historical access for Executable secured funding curves and legal category taxonomies.
- Exact public timestamp/version contract: Regulatory rule version, haircut classification and reporting entity apply as of funding decision.
- Authorized reference data (never to GitHub): Bank-specific eligible HQLA, ASF/RSF and regulatory reporting data.
- Correct edge treatment: Entity-specific regulatory implementation and internal forecasts differ; cannot reconstruct actual LCR from public totals..
- Realizable economics: Use only approved internal regulatory measures when available; funding choices constrained by entity/collateral eligibility..

## Reproducibility
Pin source URL/version/time, commit, configuration hash, calendar, random seed, solver tolerance, excluded instrument list and holdout. Preserve failed/negative tests, claims and uncertainty.

## Financial scope
$180k assumed total 24m development/data/maintenance cost; assumed launch in month 8; assumed annual gross outcome downside/base/upside $0k/$120k/$280k. Resulting 24m net ROI **-100.0% / -11.1% / 107.4% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
Scores and sensitivities are design judgments, not alpha or observed savings. Reviewer must explicitly accept evidence before moving to shadow mode.
