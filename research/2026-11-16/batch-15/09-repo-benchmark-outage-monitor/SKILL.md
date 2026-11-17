---
name: research-repo-benchmark-outage-monitor
description: Design or evaluate repo benchmark outage and revision risk monitor for United States overnight secured funding; use for the stated economic decision, point-in-time data audit, baseline challenge and falsification gates. Research workflow only; not a deployed runtime.
---

# Research Repo Benchmark Outage and Revision Risk Monitor

1. State the decision: Choose whether a funding-risk report may use a published rate, show an uncertainty interval, or require manual review; never replace a contractual fallback. Read SPEC for `QMG-20261116-09` requirements and EVALS for the frozen gate before selecting a model.
2. Resolve public sources in SOURCES first. Use reference rate x publication event x revision version; reject unlicensed payloads and missing publication times. Preserve observed, published, received, available and effective times separately.
3. Align inputs to this clock: Snapshot at 08:15 America/New_York and again after verified revisions; only information received by each timestamp is usable. A 14:30 revision must not overwrite the morning feature snapshot. Build rate release age, version chain, contingency flag and interval width. Keep future outcomes and later amendments out of features.
4. Reproduce the baseline: Carry the most recent official rate and mark missing releases only after end of day. Match risk, costs, sample, execution clock and permitted actions before testing Versioned publication-state rules plus robust short-horizon rate interval.
5. Run the domain negative test: Hide a morning release and reveal a later correction: morning output must stay immutable and explicitly uncertain; no synthetic estimate may populate a contractual-rate field. Stop on any future-data acceptance or hard-constraint violation.
6. Challenge the hypothesis: A publication-state monitor lowers material funding-risk reporting errors by at least 50% versus blindly carrying the last rate, with false escalation on fewer than 2% of ordinary releases. Apply exactly: GO if >=50% reduction in material (>2 bp monitoring error) incidents and <2% false escalation over >=250 releases plus synthetic outages; interval coverage >=99%. STOP if rare-event evidence cannot separate improvement from excessive review. Report all failed variants and effective independent sample size.
7. Review Illustrative $1bn rate-sensitive monitored exposure; no trading position. Economic value is analyst time and correction effort; excluded speculative avoided trading losses. Recompute the purely illustrative ROI using measured cost evidence if available; otherwise retain the assumption label and negative scenarios.
8. Return accept/interval/review status, immutable as-of report and official-source pointer, uncertainty, source lineage and a GO/STOP/BLOCKED verdict. Escalate Contingency/revision events are rare; injected outages are software stress tests, not evidence of historical economic benefit. OFR mean rates and official medians differ in coverage. Never trade, change contracts, deploy or claim empirical completion from this document alone.

Use PLAN for adapter boundaries and TASKS for traceability; retain immutable manifests and dependency locks when implementation is later authorized. This repository workflow is not installed as a personal ChatGPT skill.
