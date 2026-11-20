# CCP Default-Fund Mutualization Marginal Risk Budget
**Project ID:** QMG-20261120-07 · **Category:** SECURITIES FINANCE · **Score:** 89/100 (editorial) · **State:** proposal, no code/tests/empirical results.

## Market and decision
US/EU Treasury and derivatives clearing memberships. Central clearing moves bilateral exposure into waterfall and replenishment obligations that cannot be represented solely by initial-margin savings.

**Decision:** Set internal clearing exposure budgets based on potential default-fund replenishment and contingent mutualized-loss allocation.

## Explicit falsifiable research question
A conservative tail contribution metric improves risk-adjusted clearing exposure allocation against nominal balance or posted-margin controls.

## Mathematical objective (research formulation, not calibrated)
```text
RiskCharge_j=ES_alpha(sum_s MutualizedLoss_{j,s} + Replenishment_{j,s})
```
**Variables and hard constraints:** j clearing membership or CCP, s default scenario, alpha stress-tail quantile; actual waterfall order and limits are CCP specific.

## Data and timing
**Required:** Public CPMI/IOSCO disclosure framework, synthetic member default distributions, concentration factors, CCP product eligibility and fee schedules. **Observation grain:** CCP membership × cleared product × default stress scenario. **As-of rule:** Use published CCP rulebooks and dated quantitative disclosures only when released; past final stress reports cannot enter historical decisions early.

## Design options
- **Feasible baseline:** Exposure limit proportional to initial margin only.
- **Candidate research method:** Transparent worst-two-member default waterfall simulator.
- **Advanced counterfactual:** Coherent-risk allocation via Shapley/gradient ES under correlated default network scenarios.
- **Metrics:** tail capital charge, stress shortfall, liquidity buffer usage, net clearing benefit.
- **Falsification / no-go:** No material differentiation in conditional tail loss versus margin-only limits after conservative parameter uncertainty.
- **Primary leakage and identification risk:** Actual default fund contributions and replenishment terms may differ from public examples and vary by venue..

## Economic and production screening
Default fund and extra margin liquidity headroom, clearing fees and enforceable contribution caps.

**Difficulty:** Very high; **production feasibility:** Medium as stress research; **publication value:** Mutualized default-waterfall risk attribution across clearing portfolios.
**24-month ROI sensitivity:** $240k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 11 months; annual gross benefit scenarios $0k / $125k / $325k (downside/base/upside) for the remaining 1.0833333333333333 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -43.6% / 46.7%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Evidence and novelty
Unlike 2026-11-13 clearing access-path duplicate-margin optimizer, this prices mutualized *default-fund tail loss*.
- **BIS/CPMI-IOSCO Principles for Financial Market Infrastructures** (regulatory standards, published 2012-04-16): [official source](https://www.bis.org/committees/cpmi/pfmi/overview). CCP/default-waterfall research context. Individual CCP loss allocation rules must be verified.
- **SEC Treasury Clearing Implementation** (regulatory source, checked 2026-11-20): [official source](https://www.sec.gov/featured-topics/treasury-clearing-implementation). Shows Dec 31 2026 eligible cash and June 30 2027 eligible repo dates; check exemptions.

## Navigation
[Spec](SPEC.md) · [Plan](PLAN.md) · [Tasks](TASKS.md) · [Roadmap](ROADMAP.md) · [Handoff](HANDOFF.md) · [Sources](SOURCES.md) · [Agent](AGENT.md) · [Skill](SKILL.md) · [Prompt](PROMPT.md) · [Tooling](TOOLING.md) · [Workflow](WORKFLOW.md) · [Runtime](RUNTIME.md) · [Evals](EVALS.md)

**Research design only.** Market data, human approval, trading capabilities and deployable software do not yet exist in this folder.
