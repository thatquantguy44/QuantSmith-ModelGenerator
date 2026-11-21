# Korean Household Debt-Service Shock to Bank–Consumer Equity Spread
**Project ID:** QMG-20261120-14 · **Category:** DOMESTIC & GLOBAL MARKETS · **Score:** 92/100 (editorial) · **State:** proposal, no code/tests/empirical results.

## Market and decision
South Korea household credit, KOSPI/KOSDAQ banks and consumer discretionary. Aggregate debt service can change credit demand, asset quality and retail margins, but effects differ across lender and spending industries.

**Decision:** Hedge relative exposure of Korean bank and consumer equities across household debt-service regime changes.

## Explicit falsifiable research question
Lag-corrected Korean household DSR changes identify subsequent bank-versus-consumer earnings dispersion beyond policy rates/market beta.

## Mathematical objective (research formulation, not calibrated)
```text
RelativeEPS_{b,c,t+h}=a+beta*DSRSurprise_t+gamma*PolicyRate_t+delta*FX_t+epsilon
```
**Variables and hard constraints:** b bank peer basket, c consumer peer basket, h disclosure-to-outcome window; DSRSurprise uses real-time expected vs published DSR, not revised future panels.

## Data and timing
**Required:** BIS Korea household DSR, BOK/Statistics Korea public lending/rates, issuer earnings and local equity returns, reporting vintage. **Observation grain:** quarterly DSR release × issuer × accounting period × price timestamp. **As-of rule:** BIS Korean DSR published with quarterly lag (available through 2026-Q1 on checked dataset page); do not trade on 2026-Q2 unless publicly released.

## Design options
- **Feasible baseline:** Equal-beta long banks short consumer discretionary with lagged policy-rate signal.
- **Candidate research method:** Panel local projections with shrinkage and sector time fixed effects.
- **Advanced counterfactual:** Dynamic heterogeneous household credit impulse response with instrumented policy-rate shocks.
- **Metrics:** cross-sector earnings forecast delta, beta-neutral IR, worst-regime drawdown, capacity after local spreads.
- **Falsification / no-go:** No stable expected-earnings or beta-neutral sector difference once rates and economy factors are controlled.
- **Primary leakage and identification risk:** Endogenous rate policy and sector composition cause confounding; public issuer histories need delisting continuity..

## Economic and production screening
Local borrow, FX hedge, Korean market access, corporate action history, sector liquidity and taxes.

**Difficulty:** Medium-high; **production feasibility:** Medium; **publication value:** Household debt-service transmission across bank vs retail profitability.
**24-month ROI sensitivity:** $170k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 9 months; annual gross benefit scenarios $0k / $105k / $260k (downside/base/upside) for the remaining 1.25 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -22.8% / 91.2%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Evidence and novelty
Distinct from EM external debt currency mismatch and South Africa power reliability; Korean domestic household burden drives cross-sector equity dispersion.
- **BIS — South Korea household debt service ratio** (official dataset, published through 2026-Q1 as checked 2026-11-20): [official source](https://data.bis.org/topics/DSR/BIS%2CWS_DSR%2C1.0/Q.KR.H). Quarterly, delayed; sector/security matching and stock prices require other sources.

## Navigation
[Spec](SPEC.md) · [Plan](PLAN.md) · [Tasks](TASKS.md) · [Roadmap](ROADMAP.md) · [Handoff](HANDOFF.md) · [Sources](SOURCES.md) · [Agent](AGENT.md) · [Skill](SKILL.md) · [Prompt](PROMPT.md) · [Tooling](TOOLING.md) · [Workflow](WORKFLOW.md) · [Runtime](RUNTIME.md) · [Evals](EVALS.md)

**Research design only.** Market data, human approval, trading capabilities and deployable software do not yet exist in this folder.
