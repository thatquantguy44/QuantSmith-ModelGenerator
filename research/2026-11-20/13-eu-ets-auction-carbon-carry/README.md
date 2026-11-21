# EU ETS Auction Supply Revision and Carbon Futures Carry
**Project ID:** QMG-20261120-13 · **Category:** DOMESTIC & GLOBAL MARKETS · **Score:** 94/100 (editorial) · **State:** proposal, no code/tests/empirical results.

## Market and decision
EU carbon allowances (EUA), European power utilities. Auction calendar revisions and annual compliance data affect expected allowance net supply but are released on distinct clocks.

**Decision:** Hedge EUA futures calendar spreads against only announced changes in auction volume and verified-emissions obligations.

## Explicit falsifiable research question
Public-vintage auction-volume shocks improve calendar-spread/hedge-risk forecasts beyond front-month momentum and seasonal dummies.

## Mathematical objective (research formulation, not calibrated)
```text
Spread_{m,n,t}=theta*(ExpectedAuctionSupply_t - ExpectedComplianceDemand_t)+beta*EnergyControls_t+epsilon_t
```
**Variables and hard constraints:** m,n are contract maturities; expectations only use public revisions available before trade, not full-year realized auction volumes.

## Data and timing
**Required:** European Commission vintage auction calendars, Union Registry verified emissions/compliance, dated policy changes, EUA/power/gas contract prices. **Observation grain:** EU ETS auction calendar publication × allowance futures tenor × exchange quote timestamp. **As-of rule:** 2027 auction schedule announced Jul 30 2026; 2025 compliance data public Oct 5 2026; only released data at as-of permitted.

## Design options
- **Feasible baseline:** Calendar-month fixed seasonal allowance spread.
- **Candidate research method:** Event study of auction schedule revisions and futures risk factors.
- **Advanced counterfactual:** Partial equilibrium allowance banking model with endogenous industrial abatement and policy scenarios.
- **Metrics:** EUA spread basis MAE, hedged risk reduction, net carry after fees, low-liquidity scenario loss.
- **Falsification / no-go:** No out-of-sample spread forecast or hedge benefit net of spreads after matched energy factors.
- **Primary leakage and identification risk:** Policy revision expectations may be priced before official publication; futures/Registry coverage not contemporaneous..

## Economic and production screening
EUA contract liquidity, expiry rolling, carbon compliance mandates and margin/collateral limits.

**Difficulty:** High; **production feasibility:** Medium; **publication value:** Carbon allowance bankability, supply revision events and futures term structure.
**24-month ROI sensitivity:** $210k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 9 months; annual gross benefit scenarios $0k / $125k / $310k (downside/base/upside) for the remaining 1.25 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -25.6% / 84.5%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Evidence and novelty
Not prior European gas storage deliverability; models ETS allowance auction policy supply and carbon forward carry.
- **European Commission — 2026/2027 EU ETS auction calendar** (official release, 2026-07-30): [official source](https://climate.ec.europa.eu/news-other-reads/news/revised-2026-and-2027-eu-ets1-auction-calendars-published-2026-07-30_en). Calendar revisions should be stored as public vintage and not forecast from final revised schedule.
- **European Commission — Union Registry** (official dataset portal, checked 2026-11-20; annual 2025 compliance data released 2026-10-05): [official source](https://climate.ec.europa.eu/areas-action/carbon-markets/eu-emissions-trading-system-eu-ets/union-registry_en). Annual emissions/compliance data may be delayed and are not intraday allowance inventories.

## Navigation
[Spec](SPEC.md) · [Plan](PLAN.md) · [Tasks](TASKS.md) · [Roadmap](ROADMAP.md) · [Handoff](HANDOFF.md) · [Sources](SOURCES.md) · [Agent](AGENT.md) · [Skill](SKILL.md) · [Prompt](PROMPT.md) · [Tooling](TOOLING.md) · [Workflow](WORKFLOW.md) · [Runtime](RUNTIME.md) · [Evals](EVALS.md)

**Research design only.** Market data, human approval, trading capabilities and deployable software do not yet exist in this folder.
