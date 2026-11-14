# Manufactured-Dividend and Corporate-Action Loan Economics
**A · Securities finance** · **Priority 94/100** · **Difficulty Medium-high** · **Feasibility: High with corporate-action feeds** · **Publication interest 3/5 (conceptual, not a paper).**

## Why this exists
Stock loans that cross ex-dividend, split, spin-off or merger windows can change manufactured payment, operational and tax-adjusted economics.

**Market / geography:** US and cross-listed global equities. **Asset classes:** equity securities lending and corporate actions.

## Falsifiable hypothesis and investment/operational decision
Event-time aware loan optimization removes avoidable payment/operational leakage relative to fee-only renewal rules while remaining faithful to tax/legal restrictions.

**Decision:** Determine whether a permitted loan extension, pre-event return or alternative allocation is economically superior without compromising beneficial-owner legal rights..

## Research model
```text
max_(a in eligible_actions) [fee(a)-manufactured_payment_adjustment(a)-corporate_action_cost(a)-recall_cost(a)-tax_adjustment(a)]
```
a is a legally permitted loan lifecycle action; each component is booked at the owner-specific event date and in consistent after-tax units.

## Data and decision clock
Ex/record/pay dates; loan life; fee accrual; event elections; dividend amounts; owner tax flags and permitted return/recall rules. **Observation grain:** security × beneficial owner program × corporate-action event × decision timestamp. **Decision horizon:** event decisions before ex-date cutoff, using only announced corporate actions and approved tax interpretations then available.

## Baseline versus candidate
- **Baseline:** Renew if lending fee remains positive and return only upon explicit mandatory recall.
- **Proposed model:** Rule-checked event economics and constrained loan life-cycle integer optimizer.
- **Advanced option:** Scenario tree for unresolved election announcements and corporate action adjustment ranges.
- **Primary metrics:** net program income, missed payment events, operational exceptions, unauthorized action count.
- **Falsification:** Reject if post-cost incremental program income is nonpositive or event-aware policy increases mandatory-payment exceptions.
- **Primary economic or methodological caveat:** Tax withholding, treaty benefits and manufactured-dividend treatment cannot be assumed from issuer-country information alone.

## 24-month ROI sensitivity (unverified assumptions only)
USD $150k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $45k–$310k over 24 months. Net ROI = (gross benefit − cost)/cost = **-70% to 107%**. NOT forecast or historical measurement. Economic lever: illustrative prevention of a small number of high-value event-payment exceptions and legal-allowable tax drag over two years.

## Execution, capacity and feasibility
Only owner-permitted loans and action windows; supply cannot be fabricated by the optimizer.

## Research documents
[SPEC](./SPEC.md) · [PLAN](./PLAN.md) · [TASKS](./TASKS.md) · [ROADMAP](./ROADMAP.md) · [HANDOFF](./HANDOFF.md) · [SOURCES](./SOURCES.md) · [EVALS](./EVALS.md)

## Reusable agent and engineering contracts
[AGENT](./AGENT.md) · [SKILL](./SKILL.md) · [PROMPT](./PROMPT.md) · [TOOLING](./TOOLING.md) · [WORKFLOW](./WORKFLOW.md) · [RUNTIME](./RUNTIME.md)

**Status: NOT STARTED.** These are specific scientific and engineering proposals, not executable deployments, experimental findings or empirically verified strategies.
