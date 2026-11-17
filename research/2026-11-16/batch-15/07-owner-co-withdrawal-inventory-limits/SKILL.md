---
name: research-owner-co-withdrawal-inventory-limits
description: Design or evaluate owner co-withdrawal limits for lendable inventory for US and European agency lending mandates; use for the stated economic decision, point-in-time data audit, baseline challenge and falsification gates. Research workflow only; not a deployed runtime.
---

# Research Owner Co-Withdrawal Limits for Lendable Inventory

1. State the decision: Cap loans supported by correlated sources and keep replacement options against simultaneous owner withdrawals. Read SPEC for `QMG-20261116-07` requirements and EVALS for the frozen gate before selecting a model.
2. Resolve public sources in SOURCES first. Use owner x security x dated available-inventory snapshot; reject unlicensed payloads and missing publication times. Preserve observed, published, received, available and effective times separately.
3. Align inputs to this clock: Set next-day inventory limits after local close using confirmed availability received by cutoff; public fund holdings enter at filing acceptance, not portfolio as-of date. Never condition on the owner's future sale or recall notice. Build common withdrawal factor, owner lineage groups and replacement tail scenarios. Keep future outcomes and later amendments out of features.
4. Reproduce the baseline: Static 10% owner concentration cap with independent withdrawal probabilities. Match risk, costs, sample, execution clock and permitted actions before testing Hierarchical common-factor withdrawal model and CVaR allocation.
5. Run the domain negative test: Duplicate an owner under two IDs: effective diversification must not improve; simulate perfect co-withdrawal and verify the model does not report independent-source protection. Stop on any future-data acceptance or hard-constraint violation.
6. Challenge the hypothesis: Tail co-withdrawal limits reduce 99th-percentile replacement cost by at least 15% versus owner-notional caps without sacrificing more than 2% normal lending revenue. Apply exactly: GO if 99th-percentile cost improves >=15%, normal net revenue loss <=2%, and at least 3 distinct withdrawal episodes are held out; STOP if dependence is unidentified or fewer than 24 months of owner histories exist. Report all failed variants and effective independent sample size.
7. Review Illustrative $500m supported inventory; direct benefits limited to replacement-cost savings and retained fee revenue. Extreme withdrawals may have no feasible replacement regardless of model. Recompute the purely illustrative ROI using measured cost evidence if available; otherwise retain the assumption label and negative scenarios.
8. Return source concentration limits and joint-withdrawal stress certificate, uncertainty, source lineage and a GO/STOP/BLOCKED verdict. Escalate Mandate closure is not an iid recall; inactive and terminated owners must remain in the sample. Co-movement can be driven by security demand rather than shared owner behavior. Never trade, change contracts, deploy or claim empirical completion from this document alone.

Use PLAN for adapter boundaries and TASKS for traceability; retain immutable manifests and dependency locks when implementation is later authorized. This repository workflow is not installed as a personal ChatGPT skill.
