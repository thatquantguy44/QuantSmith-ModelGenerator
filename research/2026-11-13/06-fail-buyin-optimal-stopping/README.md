# Settlement-Fail Buy-In versus Wait Optimal Stopping
**A · Securities finance** · **Priority 90/100** · **Difficulty Medium** · **Feasibility: High with cost histories** · **Publication interest 4/5 (conceptual, not a paper).**

## Why this exists
A failed security delivery can become more expensive to cure over time, but immediate market buy-in can also overpay and harm relationships.

**Market / geography:** US Treasury and agency settlement. **Asset classes:** single-instruction fail management.

## Falsifiable hypothesis and investment/operational decision
A time-to-cure policy using fail penalties and executable cover costs lowers realized failure resolution expense versus fixed escalation cutoffs.

**Decision:** For an already-failed settlement instruction, decide when to cover, reroute or await delivery under documented close-out rules..

## Research model
```text
V_t(s)=min{cover_cost_t(s), reroute_cost_t(s), fail_penalty_t(s)+E[V_(t+1)(s')|s]}
```
s contains security, counterparty, days failed, available cover liquidity and contractual remedy state.

## Data and decision clock
Public dealer failure aggregates for calibration; synthetic failure life histories; approved buy-in quotes, fails charges and legal remedies. **Observation grain:** failed settlement instruction × elapsed failed day × cut-off timestamp. **Decision horizon:** business-day cure decisions only after confirmed fail and remedy eligibility.

## Baseline versus candidate
- **Baseline:** Auto-escalate after fixed N-day failure age.
- **Proposed model:** Discrete-time survival model with exact dynamic-programming stopping rule.
- **Advanced option:** Partial-observation optimal stopping with supply scarcity and stochastic cover price.
- **Primary metrics:** resolved failure days, total cure cost, forced buy-in count, missed deadline, tail loss.
- **Falsification:** Reject if holdout cost savings are below 5% or any mandated deadline is missed.
- **Primary economic or methodological caveat:** Fails charges and rights to enforce buy-ins differ by asset, market and contract; wrong assumptions invalidate decisions.

## 24-month ROI sensitivity (unverified assumptions only)
USD $130k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $65k–$260k over 24 months. Net ROI = (gross benefit − cost)/cost = **-50% to 100%**. NOT forecast or historical measurement. Economic lever: scenario: fewer unnecessary emergency cover trades on an illustrative $150m failed notional portfolio over two years.

## Execution, capacity and feasibility
Limited by available deliverable security and realistic executable cover bids.

## Research documents
[SPEC](./SPEC.md) · [PLAN](./PLAN.md) · [TASKS](./TASKS.md) · [ROADMAP](./ROADMAP.md) · [HANDOFF](./HANDOFF.md) · [SOURCES](./SOURCES.md) · [EVALS](./EVALS.md)

## Reusable agent and engineering contracts
[AGENT](./AGENT.md) · [SKILL](./SKILL.md) · [PROMPT](./PROMPT.md) · [TOOLING](./TOOLING.md) · [WORKFLOW](./WORKFLOW.md) · [RUNTIME](./RUNTIME.md)

**Status: NOT STARTED.** These are specific scientific and engineering proposals, not executable deployments, experimental findings or empirically verified strategies.
