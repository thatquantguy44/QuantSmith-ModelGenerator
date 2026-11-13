# Cash versus Noncash Loan-Collateral Economic Frontier
**A · Securities finance** · **Priority 89/100** · **Difficulty High** · **Feasibility: Medium** · **Publication interest 4/5 (conceptual, not a paper).**

## Why this exists
Collateral types impose different rebates, reinvestment limits, liquidity haircuts, indemnification capital and operational expenses, so headline loan fees are not comparable.

**Market / geography:** US and international agent lending. **Asset classes:** securities lending cash and noncash collateral.

## Falsifiable hypothesis and investment/operational decision
An all-in haircut, rebate and risk-adjusted price frontier improves loan profitability versus fee-only collateral preference.

**Decision:** Price and select borrower-offered collateral methods within owner mandate and agent legal permission..

## Research model
```text
max_(j∈allowed) [borrow_fee_j + permissible_reinvestment_yield_j - rebate_j - liquidity_cost_j - expected_loss_j - capital_j]
```
j denotes a feasible collateral convention; values must use common horizon and comparable currency-adjusted cash flows.

## Data and decision clock
Cash and noncash terms, rebate schedules, reinvestment constraints, asset eligibility, mark-to-market, haircuts and legal restrictions. **Observation grain:** loan offer × collateral type × owner mandate × quotation timestamp. **Decision horizon:** quote acceptance before loan opening with known collateral terms, not end-of-day realized earnings.

## Baseline versus candidate
- **Baseline:** Choose the highest headline loan spread among eligible offers.
- **Proposed model:** Loan-specific all-in economic break-even and constraints solver.
- **Advanced option:** Robust multi-asset collateral frontier with convex liquidity tail-risk charge.
- **Primary metrics:** net economic revenue, risk capital per dollar, haircuts and eligibility breaches, retained lending volume.
- **Falsification:** Reject if no incremental cost-adjusted profit after retaining legally admissible and service-quality constraints.
- **Primary economic or methodological caveat:** Comparing unavailable cash reinvestment yield to executable noncash economics creates phantom spread.

## 24-month ROI sensitivity (unverified assumptions only)
USD $185k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $70k–$395k over 24 months. Net ROI = (gross benefit − cost)/cost = **-62% to 114%**. NOT forecast or historical measurement. Economic lever: assume feasible switch of a small subset of a $400m average lending pool at 3–12 bps all-in uplift (unverified).

## Execution, capacity and feasibility
Constrained by approved collateral classes, reinvestment capacity, borrower credit and liquidity.

## Research documents
[SPEC](./SPEC.md) · [PLAN](./PLAN.md) · [TASKS](./TASKS.md) · [ROADMAP](./ROADMAP.md) · [HANDOFF](./HANDOFF.md) · [SOURCES](./SOURCES.md) · [EVALS](./EVALS.md)

## Reusable agent and engineering contracts
[AGENT](./AGENT.md) · [SKILL](./SKILL.md) · [PROMPT](./PROMPT.md) · [TOOLING](./TOOLING.md) · [WORKFLOW](./WORKFLOW.md) · [RUNTIME](./RUNTIME.md)

**Status: NOT STARTED.** These are specific scientific and engineering proposals, not executable deployments, experimental findings or empirically verified strategies.
