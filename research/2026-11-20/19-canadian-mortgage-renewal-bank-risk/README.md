# Canadian Mortgage Renewal Cohorts to Bank Credit-Risk Dispersion
**Project ID:** QMG-20261120-19 · **Category:** DOMESTIC & GLOBAL MARKETS · **Score:** 87/100 (editorial) · **State:** proposal, no code/tests/empirical results.

## Market and decision
Canadian banks, mortgage credit and bank equity/CDS. Fixed-mortgage renewal resets vary across vintage cohorts, producing delayed stress without an immediate change in aggregate debt stock.

**Decision:** Hedge Canadian bank credit/equity risk using public maturity-cohort mortgage renewal exposure rather than broad unemployment alone.

## Explicit falsifiable research question
Estimated vintage-conditioned payment shock predicts cross-bank loan loss and valuation dispersion beyond level rates and employment controls.

## Mathematical objective (research formulation, not calibrated)
```text
Shock_{cohort,t}=Balance_{cohort}*max(RenewalPayment_t-OldPayment,0); ECL_{bank,t+h}=beta*Shock+controls
```
**Variables and hard constraints:** Balance is refinanceable exposure (public aggregate proxy initially), ECL expected credit loss; individual bank vintage mapping may be incomplete.

## Data and timing
**Required:** Bank of Canada public mortgage balances/rates, staff renewal methodology, bank annual/quarterly mortgage disclosures, CAD rate and housing data. **Observation grain:** Canadian mortgage cohort × monthly public release × bank quarterly filing. **As-of rule:** Use released monthly tables and historical market expectations before renewal; a 2025 note's projected 2026 payments are scenario assumptions, not observed outcomes.

## Design options
- **Feasible baseline:** Bank loss sensitivity to national unemployment and policy rate alone.
- **Candidate research method:** Vintage-cohort mortgage reset microsimulation from public aggregates.
- **Advanced counterfactual:** Hierarchical hazard model linking repricing, prepayment and issuer loan-level exposures.
- **Metrics:** future loss forecast gain, bank-spread risk hedging, sensitivity to vintage assumptions, net hedging cost.
- **Falsification / no-go:** No cross-bank predictive signal after public loan books and unemployment/rate controls, or estimates too wide to act on.
- **Primary leakage and identification risk:** Public aggregate cohorts do not identify each bank's borrower vintage distribution or underwriting quality..

## Economic and production screening
TSX bank/equity/CDS liquidity, CAD FX basis, sector beta hedges and credit market impact.

**Difficulty:** Medium-high; **production feasibility:** High for aggregate stress, issuer value conditional; **publication value:** Mortgage maturity-vintage cohort stress versus bank heterogeneous ECL.
**24-month ROI sensitivity:** $160k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 8 months; annual gross benefit scenarios $0k / $105k / $240k (downside/base/upside) for the remaining 1.3333333333333333 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -12.5% / 100.0%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Evidence and novelty
Compared with Korean household DSR, this is Canadian *mortgage fixed-rate renewal cohort repricing* versus bank credit loss forecasts.
- **Bank of Canada mortgage lending flows and balances** (official dataset, monthly series checked 2026-11-20): [official source](https://www.bankofcanada.ca/rates/banking-and-financial-statistics/funds-advanced-and-outstanding-balances-for-new-and-existing-lending-by-chartered-banks/). Monthly aggregate figures, not borrower-level refinancing schedules.
- **Bank of Canada staff note on mortgage renewal** (central bank research, 2025-07): [official source](https://www.bankofcanada.ca/2025/07/staff-analytical-note-2025-21/). Published household mortgage renewal scenarios, not proof of bank relative-value alpha.

## Navigation
[Spec](SPEC.md) · [Plan](PLAN.md) · [Tasks](TASKS.md) · [Roadmap](ROADMAP.md) · [Handoff](HANDOFF.md) · [Sources](SOURCES.md) · [Agent](AGENT.md) · [Skill](SKILL.md) · [Prompt](PROMPT.md) · [Tooling](TOOLING.md) · [Workflow](WORKFLOW.md) · [Runtime](RUNTIME.md) · [Evals](EVALS.md)

**Research design only.** Market data, human approval, trading capabilities and deployable software do not yet exist in this folder.
