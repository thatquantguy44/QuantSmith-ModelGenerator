# Cash-Collateral Reinvestment Liquidity Run-Off Controller
**A · Securities finance** · **Priority 95/100** · **Difficulty High** · **Feasibility: Medium-high with authorized balances** · **Publication interest 4/5 (conceptual, not a paper).**

## Why this exists
Cash collateral received on securities loans can fund instruments whose maturity profile does not match sudden loan returns or borrower collateral recalls.

**Market / geography:** US securities lending programs. **Asset classes:** cash collateral, money-market reinvestment, lending.

## Falsifiable hypothesis and investment/operational decision
State-dependent loan run-off and reinvestment ladder simulation lowers liquidity shortfall probability versus static maturity and expected-return assumptions.

**Decision:** Allocate cash-collateral reinvestment across liquid buckets and pre-fund potential return obligations without sacrificing contractually required safety..

## Research model
```text
min_w E[funding_cost(w)+liquidity_shortfall_penalty(w)] + λ CVaR_99(shortfall(w)); Σ_k w_k=1; WAM/WAL/eligibility and liquidity floors hold
```
w_k is share in maturity/liquidity bucket k; CVaR_99 is 99% expected shortfall on repayment funding deficits, not investment P&L.

## Data and decision clock
Loan termination flows; collateral principal; reinvestment settlement and maturity ladders; redemption windows; eligible funds; short-term yields; stress scenarios. **Observation grain:** cash collateral program × reinvestment maturity bucket × business day. **Decision horizon:** end-of-day reinvestment decision with availability of prior published cash flow and eligible settlement windows.

## Baseline versus candidate
- **Baseline:** Static liquidity buffer plus duration/weighted average life constraints.
- **Proposed model:** Conditional run-off survival model combined with stochastic cash-flow gap optimizer.
- **Advanced option:** Distributionally robust multi-period policy with borrower return clustering and fire-sale haircuts.
- **Primary metrics:** 99% liquidity shortfall, reinvestment net yield, liquidity carry, stressed liquidations, breach count.
- **Falsification:** Reject if stress shortfalls are not reduced by at least 10% without degrading contractual yield or creating maturity breaches.
- **Primary economic or methodological caveat:** Return flows may cluster under crises; survivorship of reinvestment balances causes understated withdrawals.

## 24-month ROI sensitivity (unverified assumptions only)
USD $190k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $80k–$390k over 24 months. Net ROI = (gross benefit − cost)/cost = **-58% to 105%**. NOT forecast or historical measurement. Economic lever: hypothetical $600m collateral pool; avoid 1–5 days of emergency liquidity costs in a 24-month horizon; benefits depend on realized stress frequencies.

## Execution, capacity and feasibility
Capital is constrained by contractual permissible instruments, concentration, tenor limits and financing market depth.

## Research documents
[SPEC](./SPEC.md) · [PLAN](./PLAN.md) · [TASKS](./TASKS.md) · [ROADMAP](./ROADMAP.md) · [HANDOFF](./HANDOFF.md) · [SOURCES](./SOURCES.md) · [EVALS](./EVALS.md)

## Reusable agent and engineering contracts
[AGENT](./AGENT.md) · [SKILL](./SKILL.md) · [PROMPT](./PROMPT.md) · [TOOLING](./TOOLING.md) · [WORKFLOW](./WORKFLOW.md) · [RUNTIME](./RUNTIME.md)

**Status: NOT STARTED.** These are specific scientific and engineering proposals, not executable deployments, experimental findings or empirically verified strategies.
