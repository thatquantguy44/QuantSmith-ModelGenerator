# Reg SHO Locate Evidence and Borrow-Capacity Audit Engine
**Project ID:** QMG-20261120-02 · **Category:** SECURITIES FINANCE · **Score:** 95/100 (editorial) · **State:** proposal, no code/tests/empirical results.

## Market and decision
US equity securities lending and short-sale compliance. A live quote, locate assurance and subsequent borrow fill are not interchangeable, and records may cross inconsistent clocks or quantities.

**Decision:** Block or escalate a short-sale request if contemporaneous legally qualifying locate evidence or remaining documented quantity is insufficient.

## Explicit falsifiable research question
Event-sourced evidence reconstruction detects noncompliant or capacity-exhausted locates earlier than end-of-day exception review without excess false rejects.

## Mathematical objective (research formulation, not calibrated)
```text
min_policy c_FN*FN + c_FP*FP + c_D*Delay subject to permitted(request,t)<=documented_available_qty(t)
```
**Variables and hard constraints:** FN is an incorrectly accepted exception, FP an incorrectly blocked valid locate, and Delay is processing latency; all compliance rules require human-verified effective policy and exemptions.

## Data and timing
**Required:** Synthetic short-sale order events, documented locate timestamps, source identity, shares remaining, exemptions and post-trade recalls; later private desk records only if approved. **Observation grain:** short-sale request × account × security × source × event timestamp. **As-of rule:** Locate documentation and quantity must be timestamped before short sale; revised records cannot retroactively authorize prior orders.

## Design options
- **Feasible baseline:** End-of-day deterministic locate exception SQL rules.
- **Candidate research method:** Typed event-sourcing finite-state verification with causal explainability.
- **Advanced counterfactual:** Conformal anomaly scoring for ambiguous evidence routed to human review, never autonomous compliance override.
- **Metrics:** prevented invalid requests, false blocks, recall error, audit completion time, p99 latency.
- **Falsification / no-go:** Fails to flag intentionally missing/expired/overused locates on synthetic fixtures or blocks materially more valid trades than comparator.
- **Primary leakage and identification risk:** Reg SHO exemptions, broker responsibilities and settlement rules require qualified legal interpretation..

## Economic and production screening
Low per-request CPU; overhead per manual escalation and strict audit storage/retention authorization.

**Difficulty:** Medium; **production feasibility:** High for synthetic prototype; **publication value:** Temporal formal verification of short-sale locate evidence.
**24-month ROI sensitivity:** $120k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 6 months; annual gross benefit scenarios $0k / $115k / $200k (downside/base/upside) for the remaining 1.5 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / 43.8% / 150.0%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Evidence and novelty
Unlike old loan-fee selection correction, tests documentation/quantity compliance and audit proof, not fair value or pricing.
- **SEC Regulation SHO locate FAQ** (regulatory method, regulatory staff FAQ; checked 2026-11-20): [official source](https://www.sec.gov/rules-regulations/staff-guidance/trading-markets-frequently-asked-questions-8). Contains locate documentation, order-timing and exemption explanations; version applicable law before use.

## Navigation
[Spec](SPEC.md) · [Plan](PLAN.md) · [Tasks](TASKS.md) · [Roadmap](ROADMAP.md) · [Handoff](HANDOFF.md) · [Sources](SOURCES.md) · [Agent](AGENT.md) · [Skill](SKILL.md) · [Prompt](PROMPT.md) · [Tooling](TOOLING.md) · [Workflow](WORKFLOW.md) · [Runtime](RUNTIME.md) · [Evals](EVALS.md)

**Research design only.** Market data, human approval, trading capabilities and deployable software do not yet exist in this folder.
