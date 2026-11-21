# Noncash Collateral Correlation-Cluster Haircut Controller
**Project ID:** QMG-20261120-06 · **Category:** SECURITIES FINANCE · **Score:** 90/100 (editorial) · **State:** proposal, no code/tests/empirical results.

## Market and decision
Multi-asset collateral supporting US/EU securities loans. Static issuer/security-class haircuts can understate simultaneous stress of correlated noncash collateral while overhaircutting diversified pools.

**Decision:** Recommend minimum defensive haircuts for a collateral basket based on joint concentration and liquidation correlation.

## Explicit falsifiable research question
Cluster-aware chance constraints produce lower stressed shortfall than sector-flat haircuts at a matched average financing cost.

## Mathematical objective (research formulation, not calibrated)
```text
min_h CarryCost(h) subject to P(Loss(Collateral,Loan,h)>Limit)<=alpha and issuer_weight<=cap
```
**Variables and hard constraints:** h is haircut vector, alpha tolerated tail probability and cap issuer concentration; credit/legal eligibility are hard constraints.

## Data and timing
**Required:** Approved collateral constituents, synthetic issuer cross-holdings, stressed factor returns, liquidation bid/ask, haircut and legal threshold. **Observation grain:** collateral security × issuer cluster × loan exposure × as-of time. **As-of rule:** Apply only return histories, prices, group linkages and issuer memberships known at the decision timestamp.

## Design options
- **Feasible baseline:** Uniform issuer/asset-class static haircut.
- **Candidate research method:** Scenario CVaR optimization with issuer cluster caps.
- **Advanced counterfactual:** Distributionally robust ambiguity-set CVaR with wrong-way liquidity correlation.
- **Metrics:** shortfall ES, collateral usage, haircut turnover, stress exceptions.
- **Falsification / no-go:** Risk benefit disappears when using stressed-correlation holdouts or violates legal haircut floors.
- **Primary leakage and identification risk:** Asset covariance may break exactly when haircuts are needed and public free-float proxies omit liquidation controls..

## Economic and production screening
Financing spread effects, haircuts, asset transfer restrictions, concentration penalties and market impact.

**Difficulty:** High; **production feasibility:** Medium with approved data; **publication value:** Distributionally robust collateral concentration and shadow financing cost.
**24-month ROI sensitivity:** $210k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 9 months; annual gross benefit scenarios $0k / $145k / $320k (downside/base/upside) for the remaining 1.25 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -13.7% / 90.5%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Evidence and novelty
Not stale-mark quarantine (price integrity) or wrong-way *borrower default* risk: chooses collateral cluster haircut policy at portfolio level.
- **OFR U.S. Repo Markets Data Release** (public data, current methodology page; checked 2026-11-20): [official source](https://www.financialresearch.gov/short-term-funding-monitor/datasets/repo/). Cleared rates typically T+1; tri-party T+2; participant-level graph not public.
- **BIS/CPMI-IOSCO Principles for Financial Market Infrastructures** (regulatory standards, published 2012-04-16): [official source](https://www.bis.org/committees/cpmi/pfmi/overview). CCP/default-waterfall research context. Individual CCP loss allocation rules must be verified.

## Navigation
[Spec](SPEC.md) · [Plan](PLAN.md) · [Tasks](TASKS.md) · [Roadmap](ROADMAP.md) · [Handoff](HANDOFF.md) · [Sources](SOURCES.md) · [Agent](AGENT.md) · [Skill](SKILL.md) · [Prompt](PROMPT.md) · [Tooling](TOOLING.md) · [Workflow](WORKFLOW.md) · [Runtime](RUNTIME.md) · [Evals](EVALS.md)

**Research design only.** Market data, human approval, trading capabilities and deployable software do not yet exist in this folder.
