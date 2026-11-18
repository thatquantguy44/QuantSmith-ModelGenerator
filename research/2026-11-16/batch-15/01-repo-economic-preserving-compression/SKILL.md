---
name: research-repo-economic-preserving-compression
description: Design or evaluate repo compression with cash-flow preservation for US Treasury repo; one legal netting set at a time; use for the stated economic decision, point-in-time data audit, baseline challenge and falsification gates. Research workflow only; not a deployed runtime.
---

# Research Repo Compression with Cash-Flow Preservation

1. State the decision: Select existing tickets to tear up or resize without changing each participant's dated cash and CUSIP obligations. Read SPEC for `QMG-20261116-01` requirements and EVALS for the frozen gate before selecting a model.
2. Resolve public sources in SOURCES first. Use repo ticket and dated cash/security obligation; reject unlicensed payloads and missing publication times. Preserve observed, published, received, available and effective times separately.
3. Align inputs to this clock: Freeze the ledger at 14:00 America/New_York; use only confirmed records ingested by 13:55 and decisions before the relevant service cutoff. Cash-flow amendments received later enter the next solve. Build dated incidence matrices, lot constraints and consent mask. Keep future outcomes and later amendments out of features.
4. Reproduce the baseline: Cancel exact opposite tickets bilaterally within a legal set; otherwise hold the original book. Match risk, costs, sample, execution clock and permitted actions before testing Mixed-integer minimum-cost circulation with exact cash-flow conservation.
5. Run the domain negative test: Construct a three-node cycle with mismatched maturity dates: it must remain uncompressed; changing one consent flag must remove every affected action. Stop on any future-data acceptance or hard-constraint violation.
6. Challenge the hypothesis: An economics-preserving compression reduces eligible gross ticket notional by at least 15% and operational cost by at least 10% versus bilateral pair cancellation, with no additional settlement or market risk. Apply exactly: GO only with >=15% gross reduction and >=10% realized operational cost reduction on held-out eligible sets; every cash/security residual <=$0.01 cash or zero security units; zero consent violations. STOP on any economic transfer or if gains vanish after legal filtering. Report all failed variants and effective independent sample size.
7. Review Illustrative $1bn eligible matched book; no directional risk capital assumed. Economics come from fewer messages and approved gross-capacity charges, not treating all removed notional as regulatory capital relief. Recompute the purely illustrative ROI using measured cost evidence if available; otherwise retain the assumption label and negative scenarios.
8. Return proposed tear-up/resizing schedule, exact flow certificate and rejected-action reasons, uncertainty, source lineage and a GO/STOP/BLOCKED verdict. Escalate Legal netting is not created by algebra; different dates, rates and counterparties must not be silently offset. Synthetic network density can overstate capacity. Never trade, change contracts, deploy or claim empirical completion from this document alone.

Use PLAN for adapter boundaries and TASKS for traceability; retain immutable manifests and dependency locks when implementation is later authorized. This repository workflow is not installed as a personal ChatGPT skill.
