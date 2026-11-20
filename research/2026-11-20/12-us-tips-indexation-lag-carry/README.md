# US TIPS CPI Indexation-Lag Carry and Breakeven Calendar Surface
**Project ID:** QMG-20261120-12 · **Category:** DOMESTIC & GLOBAL MARKETS · **Score:** 95/100 (editorial) · **State:** proposal, no code/tests/empirical results.

## Market and decision
US TIPS, nominal Treasuries, inflation swaps. TIPS index ratio uses reference CPI with publication lag; naïve inflation beta ignores fixed-known indexation accrual and deflation mechanics.

**Decision:** Select TIPS versus nominal duration-hedged exposure around CPI index-ratio carry windows.

## Explicit falsifiable research question
A vintage-consistent carry decomposition improves matched-duration real-vs-nominal excess-return hedging net of liquidity/rollover costs.

## Mathematical objective (research formulation, not calibrated)
```text
TIPSReturn_t=RealYieldReturn_t+KnownIndexAccrual_t+InflationNews_t+LiquidityResidual_t
```
**Variables and hard constraints:** KnownIndexAccrual_t is observable at decision time; carry, breakeven and real-yield exposures require duration scaling and deflation floors.

## Data and timing
**Required:** Treasury official daily TIPS index ratios/CPI, vintage BLS CPI, nominal/TIPS quotes, issue terms, accrued interest. **Observation grain:** TIPS CUSIP × CPI/index-ratio effective date × decision timestamp. **As-of rule:** Daily index ratios can be forecast only from already published reference CPI; preserve first release and later corrections.

## Design options
- **Feasible baseline:** Duration-matched TIPS-minus-nominal bond without CPI-calendar signal.
- **Candidate research method:** Deterministic index-ratio accrual and liquidity-factor attribution.
- **Advanced counterfactual:** State-space real/nominal curve with stochastic CPI surprise and inflation floor convexity.
- **Metrics:** hedge tracking error, information ratio net of costs, index replication error, carry decomposition residual.
- **Falsification / no-go:** Improvement vanishes versus a carry-only and time-matched duration hedge after execution spread costs.
- **Primary leakage and identification risk:** Illiquid issue quotations, inflation floor optionality, unrevised CPI data and seasonality overfit..

## Economic and production screening
Issue-level depth, coupon accrued interest, repo funding, bid-ask, tax and duration hedging constraints.

**Difficulty:** Medium; **production feasibility:** High as price replication; **publication value:** Point-in-time inflation-linked bond carry and indexation-lag mispricing decomposition.
**24-month ROI sensitivity:** $135k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 6 months; annual gross benefit scenarios $0k / $105k / $200k (downside/base/upside) for the remaining 1.5 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / 16.7% / 122.2%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Evidence and novelty
Prior US-Euro sovereign curve shock model decomposes release shocks; this prices U.S. issue-specific TIPS CPI indexation carry.
- **U.S. Treasury Fiscal Data — TIPS and CPI** (public data, last updated 2026-11-10): [official source](https://fiscaldata.treasury.gov/datasets/tips-cpi-data/). Monthly and daily ratios; preserve publication time and revision flags; securities prices require separate data.
- **SEC EDGAR API documentation** (public data API, updated 2025-04-08): [official source](https://www.sec.gov/search-filings/edgar-application-programming-interfaces). Companyfacts is not a complete source of issuer/customer segmentation or historical index membership.

## Navigation
[Spec](SPEC.md) · [Plan](PLAN.md) · [Tasks](TASKS.md) · [Roadmap](ROADMAP.md) · [Handoff](HANDOFF.md) · [Sources](SOURCES.md) · [Agent](AGENT.md) · [Skill](SKILL.md) · [Prompt](PROMPT.md) · [Tooling](TOOLING.md) · [Workflow](WORKFLOW.md) · [Runtime](RUNTIME.md) · [Evals](EVALS.md)

**Research design only.** Market data, human approval, trading capabilities and deployable software do not yet exist in this folder.
