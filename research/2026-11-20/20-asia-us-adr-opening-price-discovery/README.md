# Asia–US Cross-Listed ADR Opening Auction Information Transfer
**Project ID:** QMG-20261120-20 · **Category:** DOMESTIC & GLOBAL MARKETS · **Score:** 86/100 (editorial) · **State:** proposal, no code/tests/empirical results.

## Market and decision
US ADRs and Korea/Japan/Taiwan/Hong Kong local shares. Local home-market closes and US ADR opening auctions occur asynchronously; simplistic close-to-open arbitrage ignores FX, share conversion and spreads.

**Decision:** Choose hedge and execution timing for US ADR versus home-market overnight fair value.

## Explicit falsifiable research question
An asynchronous local-information estimator reduces US ADR opening-price execution error beyond last local close plus FX conversion.

## Mathematical objective (research formulation, not calibrated)
```text
FairADR_{i,t}=Ratio_i*LocalPrice_{i,homeclose}*FX_{i,t}+CrossMarketNews_{i,t}
```
**Variables and hard constraints:** Ratio_i is point-in-time ADR share ratio, FX has correct currency direction, CrossMarketNews is post-local close information known before US auction.

## Data and timing
**Required:** Issuer depositary receipts ratios, local listings, public filings, FX quote timestamps, US ADR opening auctions, dividends and corporate action history. **Observation grain:** ADR × home-market session × US opening-auction timestamp. **As-of rule:** Prevent local-price forward fill across sessions; ratio/corporate actions must be known at the US quote decision time.

## Design options
- **Feasible baseline:** Last home close × publicly known ADR conversion ratio × contemporaneous FX spot.
- **Candidate research method:** State-space asynchronous Kalman fair-value update using futures and related peer prices.
- **Advanced counterfactual:** Continuous-time latent-price discovery with joint jump and optimal execution inventory control.
- **Metrics:** auction fair-value error, paired realized slippage, inventory risk, settlement/convertibility feasibility.
- **Falsification / no-go:** No consistent opening execution improvement after financing, foreign exchange, depositary and auction spread costs.
- **Primary leakage and identification risk:** ADR conversion fees, access restrictions, local holidays and stale home quotes create phantom arbitrage..

## Economic and production screening
ADR opening auction depth, ADR conversion channel capacity, local/US holiday and FX hedging constraints.

**Difficulty:** High; **production feasibility:** Medium; **publication value:** Asynchronous global price discovery with share-class conversion friction.
**24-month ROI sensitivity:** $225k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 10 months; annual gross benefit scenarios $0k / $120k / $310k (downside/base/upside) for the remaining 1.1666666666666667 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -37.8% / 60.7%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Evidence and novelty
Prior global covariance regime and FX hedge programs forecast portfolio risk; this models cross-listed single-name auction lead-lag with depositary mechanics.
- **SEC developer resources and disclosure revisions** (public filings methodology, checked 2026-11-20): [official source](https://www.sec.gov/search-filings/edgar-search-assistance/accessing-edgar-data). Public filings can be corrected; store original accepted filing before any update.
- **SEC EDGAR API documentation** (public data API, updated 2025-04-08): [official source](https://www.sec.gov/search-filings/edgar-application-programming-interfaces). Companyfacts is not a complete source of issuer/customer segmentation or historical index membership.

## Navigation
[Spec](SPEC.md) · [Plan](PLAN.md) · [Tasks](TASKS.md) · [Roadmap](ROADMAP.md) · [Handoff](HANDOFF.md) · [Sources](SOURCES.md) · [Agent](AGENT.md) · [Skill](SKILL.md) · [Prompt](PROMPT.md) · [Tooling](TOOLING.md) · [Workflow](WORKFLOW.md) · [Runtime](RUNTIME.md) · [Evals](EVALS.md)

**Research design only.** Market data, human approval, trading capabilities and deployable software do not yet exist in this folder.
