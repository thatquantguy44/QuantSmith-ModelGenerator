# ETF Creation/Redemption Basket Shock to Stock-Loan Supply
**Project ID:** QMG-20261120-05 · **Category:** SECURITIES FINANCE · **Score:** 91/100 (editorial) · **State:** proposal, no code/tests/empirical results.

## Market and decision
US equity ETFs and underlying stock loan. An ETF primary-market basket can move specific equities and temporarily reshape lendable inventory and market demand independent of secondary price returns.

**Decision:** Reserve lendable constituent supply ahead of known or forecasted ETF in-kind redemption/creation windows.

## Explicit falsifiable research question
Point-in-time basket-flow measures predict incremental short-horizon available-to-lend changes beyond conventional index membership and short-interest proxies.

## Mathematical objective (research formulation, not calibrated)
```text
DeltaSupply_{i,t+h}=alpha_i+beta*BasketsDelta_{i,t}+gamma*Controls_{i,t}+epsilon
```
**Variables and hard constraints:** i is CUSIP, h forecast horizon, basket delta is an appropriately signed and actually available in-kind constituent-flow measure; no lookahead custom basket files.

## Data and timing
**Required:** ETF disclosed holdings and creation units, public filings, official membership events, licensed AP basket/flows and loan availability for later study. **Observation grain:** ETF × constituent × creation/redemption day × publication time. **As-of rule:** Only baskets available to a decision-maker before ETF order cutoff may be used; end-of-day holding reports are not morning baskets.

## Design options
- **Feasible baseline:** Change in ETF shares outstanding plus index-event dummy.
- **Candidate research method:** Hierarchical event study with issuer-basket aggregation and controls.
- **Advanced counterfactual:** Instrumented flow shock model addressing ETF price-demand endogeneity.
- **Metrics:** inventory forecast MAE, short availability calibration, incremental net inventory carry, execution slippage.
- **Falsification / no-go:** No incremental held-out inventory signal after availability alignment and underlying stock flow controls.
- **Primary leakage and identification risk:** Most executable AP basket details and actual stock-loan supply are not public..

## Economic and production screening
Inventory is limited by mandate, lendability and recalls; transaction fees and timing dominate thin basket effects.

**Difficulty:** High; **production feasibility:** Medium with licensed data; **publication value:** ETF plumbing and endogenous securities lending supply transmission.
**24-month ROI sensitivity:** $190k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 9 months; annual gross benefit scenarios $0k / $130k / $280k (downside/base/upside) for the remaining 1.25 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -14.5% / 84.2%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Evidence and novelty
Distinct from synthetic borrow put-call parity and owner's co-withdrawal risk; identifies ETF primary basket supply as separate driver.
- **SEC EDGAR API documentation** (public data API, updated 2025-04-08): [official source](https://www.sec.gov/search-filings/edgar-application-programming-interfaces). Companyfacts is not a complete source of issuer/customer segmentation or historical index membership.
- **SEC developer resources and disclosure revisions** (public filings methodology, checked 2026-11-20): [official source](https://www.sec.gov/search-filings/edgar-search-assistance/accessing-edgar-data). Public filings can be corrected; store original accepted filing before any update.

## Navigation
[Spec](SPEC.md) · [Plan](PLAN.md) · [Tasks](TASKS.md) · [Roadmap](ROADMAP.md) · [Handoff](HANDOFF.md) · [Sources](SOURCES.md) · [Agent](AGENT.md) · [Skill](SKILL.md) · [Prompt](PROMPT.md) · [Tooling](TOOLING.md) · [Workflow](WORKFLOW.md) · [Runtime](RUNTIME.md) · [Evals](EVALS.md)

**Research design only.** Market data, human approval, trading capabilities and deployable software do not yet exist in this folder.
