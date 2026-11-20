# Securities-Lending Circular Flow Surveillance via Temporal Graphs
**Project ID:** QMG-20261120-10 · **Category:** SECURITIES FINANCE · **Score:** 86/100 (editorial) · **State:** proposal, no code/tests/empirical results.

## Market and decision
Multi-agent securities loans and collateral transfers; US/EU. Pairwise exception rules can miss cyclic chains of small loans and rapid reversals through multiple legal counterparties.

**Decision:** Escalate suspicious short-lived circular borrow/return patterns for compliance review without inferring wrongdoing from volume alone.

## Explicit falsifiable research question
Causal temporal-motif alerts improve precision at fixed review capacity over pairwise round-trip thresholds in seeded synthetic cases.

## Mathematical objective (research formulation, not calibrated)
```text
min_alertPolicy ReviewCost + MissCost subject to ReviewCapacity<=K and no autonomously adverse action
```
**Variables and hard constraints:** K is review budget; temporal motif score must be conditioned on legitimate inventory transfers and settlement cycles.

## Data and timing
**Required:** Synthetic multi-party loan/return event graph, matched collateral movement, legitimate transfer controls, anonymized case annotations if permitted. **Observation grain:** synthetic securities loan transfer edge × security × event timestamp. **As-of rule:** Create graph only from recorded transfers visible before alert time; disallow knowledge of subsequent investigation outcomes in features.

## Design options
- **Feasible baseline:** Two-party net-quantity turnaround rules.
- **Candidate research method:** Temporal graph motif detection with exact deterministic event identity.
- **Advanced counterfactual:** Weakly supervised dynamic graph anomaly ranking with human-in-loop conformal calibration.
- **Metrics:** precision at K, seeded motif recall, legitimate-flow false-alerts, explanation fidelity.
- **Falsification / no-go:** No precision@K gain against pairwise rules under benign high-volume churn fixtures.
- **Primary leakage and identification risk:** False accusations, privileged customer data, and severe sample-selection bias in investigated cases..

## Economic and production screening
Compliance analyst review capacity and evidentiary retention, no automatic client suspension.

**Difficulty:** High; **production feasibility:** Medium with strict controls; **publication value:** Temporal graph surveillance with constrained false accusations.
**24-month ROI sensitivity:** $165k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 9 months; annual gross benefit scenarios $0k / $95k / $240k (downside/base/upside) for the remaining 1.25 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -28.0% / 81.8%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Evidence and novelty
Batch-14 cross-book identity reconciler targets *record matching*; this tests suspicious multi-party circular behavior at a fixed review budget.
- **ESMA Securities Financing Transactions Reporting** (regulatory source, current reporting framework checked 2026-11-20): [official source](https://www.esma.europa.eu/data-reporting/sftr-reporting). Public reports are aggregates; transaction-level SFTR is permissioned.
- **SEC Regulation SHO locate FAQ** (regulatory method, regulatory staff FAQ; checked 2026-11-20): [official source](https://www.sec.gov/rules-regulations/staff-guidance/trading-markets-frequently-asked-questions-8). Contains locate documentation, order-timing and exemption explanations; version applicable law before use.

## Navigation
[Spec](SPEC.md) · [Plan](PLAN.md) · [Tasks](TASKS.md) · [Roadmap](ROADMAP.md) · [Handoff](HANDOFF.md) · [Sources](SOURCES.md) · [Agent](AGENT.md) · [Skill](SKILL.md) · [Prompt](PROMPT.md) · [Tooling](TOOLING.md) · [Workflow](WORKFLOW.md) · [Runtime](RUNTIME.md) · [Evals](EVALS.md)

**Research design only.** Market data, human approval, trading capabilities and deployable software do not yet exist in this folder.
