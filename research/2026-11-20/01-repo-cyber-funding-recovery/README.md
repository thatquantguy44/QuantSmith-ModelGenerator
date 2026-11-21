# Cyber-Outage Contingent Repo Funding Recovery Routes
**Project ID:** QMG-20261120-01 · **Category:** SECURITIES FINANCE · **Score:** 96/100 (editorial) · **State:** proposal, no code/tests/empirical results.

## Market and decision
US cleared and tri-party repo. A temporary lender or settlement-node cyber outage can strand otherwise sound secured funding even with sufficient collateral.

**Decision:** Pre-approve alternate cash-lender/clearing routes and reserve a minimum contingency liquidity buffer for an exogenous operational outage.

## Explicit falsifiable research question
Conditional multi-route recovery decreases funding shortfall and expected disruption cost more than an equal-cost static backup buffer.

## Mathematical objective (research formulation, not calibrated)
```text
min_{x,b} E_s[ FundingGap_s(x,b)*p_s + SwitchingCost_s(x) ] + CarryCost(b)
```
**Variables and hard constraints:** x are route and lender allocation decisions, b is reserved liquidity, p_s is the unit shortfall penalty in outage scenario s; legal availability, committed limits and collateral eligibility bound x.

## Data and timing
**Required:** Timestamped anonymized funding route uptime, fallback approvals, cutoff times, public OFR repo volumes/rates, synthetic outage schedules. **Observation grain:** route × lender class × hourly outage scenario. **As-of rule:** OFR cleared rate/volume normally T+1 and tri-party T+2, so use public series as lagged calibration only; route outage telemetry must be timestamped pre-decision.

## Design options
- **Feasible baseline:** Fixed 10% contingency funding buffer with one permitted fallback.
- **Candidate research method:** Two-stage robust multi-commodity flow with cyber failure scenarios.
- **Advanced counterfactual:** Distributionally robust scenario-tree route control with simultaneous correlated cash-lender disruptions.
- **Metrics:** shortfall dollars, p95 duration, liquidity carry, fail probability, recovery cost.
- **Falsification / no-go:** Held-out synthetic/approved outage replay fails to reduce mean + tail shortfall at fixed total contingency cost.
- **Primary leakage and identification risk:** Public aggregates cannot recover the bank-level cash-lender network or prove an actual route is legally available..

## Economic and production screening
Route/credit limits, settlement windows, cleared access and fallback switching charges; no publicly executable orders.

**Difficulty:** High; **production feasibility:** Conditional; **publication value:** Stochastic financial network recovery and operational shock simulation.
**24-month ROI sensitivity:** $220k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 9 months; annual gross benefit scenarios $0k / $180k / $340k (downside/base/upside) for the remaining 1.25 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / 2.3% / 93.2%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Evidence and novelty
Distinct from batch-15 benchmark-outage monitoring: this optimizes funding continuity under cyber node failure, not price publication.
- **OFR working paper — Short Circuiting Short-Term Funding** (working paper, 2026-02-10): [official source](https://www.financialresearch.gov/working-papers/2026/02/10/short-circuiting-short-term-funding/). Empirical cyber outage simulation context, not a validation of this proposed controller.
- **OFR U.S. Repo Markets Data Release** (public data, current methodology page; checked 2026-11-20): [official source](https://www.financialresearch.gov/short-term-funding-monitor/datasets/repo/). Cleared rates typically T+1; tri-party T+2; participant-level graph not public.
- **SEC Treasury Clearing Implementation** (regulatory source, checked 2026-11-20): [official source](https://www.sec.gov/featured-topics/treasury-clearing-implementation). Shows Dec 31 2026 eligible cash and June 30 2027 eligible repo dates; check exemptions.

## Navigation
[Spec](SPEC.md) · [Plan](PLAN.md) · [Tasks](TASKS.md) · [Roadmap](ROADMAP.md) · [Handoff](HANDOFF.md) · [Sources](SOURCES.md) · [Agent](AGENT.md) · [Skill](SKILL.md) · [Prompt](PROMPT.md) · [Tooling](TOOLING.md) · [Workflow](WORKFLOW.md) · [Runtime](RUNTIME.md) · [Evals](EVALS.md)

**Research design only.** Market data, human approval, trading capabilities and deployable software do not yet exist in this folder.
