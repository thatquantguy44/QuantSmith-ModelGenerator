---
name: research-securities-loan-dust-lot-consolidation
description: Design or evaluate securities-loan dust-lot consolidation for US and developed-market equity lending; use for the stated economic decision, point-in-time data audit, baseline challenge and falsification gates. Research workflow only; not a deployed runtime.
---

# Research Securities-Loan Dust-Lot Consolidation

1. State the decision: Consolidate or close eligible small lots within the same owner/borrower/legal permissions while preserving economic exposure and service constraints. Read SPEC for `QMG-20261116-10` requirements and EVALS for the frozen gate before selecting a model.
2. Resolve public sources in SOURCES first. Use owner x borrower x security loan lot x service day; reject unlicensed payloads and missing publication times. Preserve observed, published, received, available and effective times separately.
3. Align inputs to this clock: Solve after confirmed end-of-day books and before next-day instruction cutoff; only booked demand and valid consent known at solve time enter. Settled movements are later outcomes. Build fixed servicing charge, permitted owner-lot map and movement-cost matrix. Keep future outcomes and later amendments out of features.
4. Reproduce the baseline: Pro-rata eligible allocation across owners, subject to existing concentration caps. Match risk, costs, sample, execution clock and permitted actions before testing Fixed-charge transportation MILP.
5. Run the domain negative test: Set per-ticket cost to zero: consolidation must not invent savings; introduce an owner-specific nontransferability flag and verify its lot remains untouched. Stop on any future-data acceptance or hard-constraint violation.
6. Challenge the hypothesis: Integer cost-aware lot consolidation cuts recurring servicing expense by at least 20% relative to pro-rata allocation without reducing net lending revenue by more than 1%. Apply exactly: GO if >=20% servicing-cost saving and <=1% net revenue loss, zero owner-rights violations and payback within 12 months on measured cost inputs. STOP if gains disappear after movement fees or permitted allocations are fixed. Report all failed variants and effective independent sample size.
7. Review Illustrative 50,000 serviced lots per year; no market ADV capacity claim. Benefits limited by actual removable lots and movement/consent cost, not gross notional. Recompute the purely illustrative ROI using measured cost evidence if available; otherwise retain the assumption label and negative scenarios.
8. Return consolidation suggestions with per-owner exposure/revenue reconciliation, uncertainty, source lineage and a GO/STOP/BLOCKED verdict. Escalate Tax lots, revenue attribution, beneficial-owner fairness and contract permissions can prohibit economically appealing consolidation. Unit-cost assumptions often dominate the result. Never trade, change contracts, deploy or claim empirical completion from this document alone.

Use PLAN for adapter boundaries and TASKS for traceability; retain immutable manifests and dependency locks when implementation is later authorized. This repository workflow is not installed as a personal ChatGPT skill.
