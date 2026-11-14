# Treasury Clearing Access-Path & Duplicate-Margin Optimizer
**A · Securities finance** · **Priority 97/100** · **Difficulty High** · **Feasibility: High conditional on clearing data** · **Publication interest 4/5 (conceptual, not a paper).**

## Why this exists
Direct, sponsored and agent clearing routes may impose different netting, margin, liquidity and access costs; a lower repo rate can still be a more expensive end-to-end financing route.

**Market / geography:** United States; cleared cash Treasury and repo. **Asset classes:** Treasury cash, repo, FICC access.

## Falsifiable hypothesis and investment/operational decision
Path-aware margin, clearing fees and funding costs change the optimal routing mix and reduce total economically consumed liquidity relative to selecting the lowest quoted repo rate.

**Decision:** Route eligible Treasury financing activity among legally permitted clearing access paths and participant entities while honoring CCP and customer-protection constraints..

## Research model
```text
min_(x_p) Σ_p x_p*(rate_p*notional*T + fee_p + margin_carry_p + default_fund_p + cclf_liquidity_p) - verified_netting_benefit(x); Σ_p x_p=1; x_p=0 for ineligible paths
```
x_p is fraction routed through path p; T is year-fraction tenor; margin, default fund, CCLF and netting effects use validated path-specific rules rather than assumed offsets.

## Data and decision clock
Eligible trade templates; path availability; historical quote spreads; initial/variation margin stress; capital/CCLF allocation; modeled netting sets; direct/sponsored/agent fees. **Observation grain:** trade × eligible clearing access path × decision timestamp. **Decision horizon:** trade routing decision at quote acceptance; historical public aggregates are lagged and cannot be used as intraday quotes.

## Baseline versus candidate
- **Baseline:** Minimize executable repo rate ignoring path-specific costs, after validating that every route is eligible.
- **Proposed model:** Mixed-integer convex routing with separate margin, settlement and liquidity shadow prices.
- **Advanced option:** Stochastic two-stage CCP-margin and default-fund planning with cross-netting robustness.
- **Primary metrics:** USD all-in funding cost, dollar liquidity encumbrance, margin stress p99, ineligible route count, rejection rate.
- **Falsification:** Reject if simulated net savings are below 2 bps of affected financing notional or vanish under independently validated margin rules.
- **Primary economic or methodological caveat:** Clearing rule exemptions and netting eligibility vary; estimated margin offsets could be nonportable across entities.

## 24-month ROI sensitivity (unverified assumptions only)
USD $280k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $160k–$620k over 24 months. Net ROI = (gross benefit − cost)/cost = **-43% to 121%**. NOT forecast or historical measurement. Economic lever: assume 2–8 bps avoidable total cost on an eligible hypothetical $250m continuously financed at ~1yr equivalent and fraction of volume attainable; capture model must account for actual turnover.

## Execution, capacity and feasibility
Constrained by FICC participant access, available repo quote depth, account/entity eligibility and netting-set segregation.

## Research documents
[SPEC](./SPEC.md) · [PLAN](./PLAN.md) · [TASKS](./TASKS.md) · [ROADMAP](./ROADMAP.md) · [HANDOFF](./HANDOFF.md) · [SOURCES](./SOURCES.md) · [EVALS](./EVALS.md)

## Reusable agent and engineering contracts
[AGENT](./AGENT.md) · [SKILL](./SKILL.md) · [PROMPT](./PROMPT.md) · [TOOLING](./TOOLING.md) · [WORKFLOW](./WORKFLOW.md) · [RUNTIME](./RUNTIME.md)

**Status: NOT STARTED.** These are specific scientific and engineering proposals, not executable deployments, experimental findings or empirically verified strategies.
