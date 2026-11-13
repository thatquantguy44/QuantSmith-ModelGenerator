# EM External-Funding Fragility via Currency Mismatch and IIP
**B · Domestic & global markets** · **Priority 94/100** · **Difficulty Medium-high** · **Feasibility: High for quarterly research** · **Publication interest 5/5 (conceptual, not a paper).**

## Why this exists
A country can appear resilient on debt/GDP yet be fragile to dollar funding when external liabilities and liquid FX buffers have unfavorable maturity or currency composition.

**Market / geography:** Brazil, Mexico, South Africa, Indonesia, India and selected EM sovereigns. **Asset classes:** EM FX, sovereign risk, global macro.

## Falsifiable hypothesis and investment/operational decision
Release-vintage normalized foreign-currency credit-to-external-assets mismatch predicts EM stress windows beyond carry and spot volatility.

**Decision:** Size EM FX downside budgets and sovereign duration exposures before external-funding shocks..

## Research model
```text
Fragility_c,t=(FX_credit_c,t - liquid_FX_assets_c,t)/GDP_c,t + λ*short_debt_service_c,t; optimize w for worst-case loss
```
c denotes country; all stocks denominated in comparable FX units; FX-credit and external-assets proxies can have incompatible reporting definitions requiring explicit normalization.

## Data and decision clock
IMF IIP, BIS global liquidity quarterly FX credit, OECD macro where available, public reserve series and FX/sovereign returns. **Observation grain:** country × reporting quarter × first-public-availability time. **Decision horizon:** quarterly risk changes after actual statistical release; never refresh historic positions with today's revised values.

## Baseline versus candidate
- **Baseline:** Traditional sovereign credit rating tier, FX carry and three-month realized volatility.
- **Proposed model:** Point-in-time standardized funding mismatch factor with recession/regime interactions.
- **Advanced option:** Joint skewed macro-financial state-space with robust optimization and missing vintage uncertainty.
- **Primary metrics:** EM FX crash recall, max drawdown, FX-adjusted stress Brier, portfolio VaR breaches.
- **Falsification:** Reject if stress recall or drawdown control fails to beat carry-vol baseline in holdout crises.
- **Primary economic or methodological caveat:** Global liquidity metrics are quarterly; imputed weekly updates are model estimates, not observations.

## 24-month ROI sensitivity (unverified assumptions only)
USD $125k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $0k–$355k over 24 months. Net ROI = (gross benefit − cost)/cost = **-100% to 184%**. NOT forecast or historical measurement. Economic lever: hypothetical liquid $15m EM risk allocation where a small fraction of crash drawdown is avoided; no empirical hedge benefit.

## Execution, capacity and feasibility
Use liquid EM FX forwards/ETFs only where available; include carry, forward points, market depth and capital controls.

## Research documents
[SPEC](./SPEC.md) · [PLAN](./PLAN.md) · [TASKS](./TASKS.md) · [ROADMAP](./ROADMAP.md) · [HANDOFF](./HANDOFF.md) · [SOURCES](./SOURCES.md) · [EVALS](./EVALS.md)

## Reusable agent and engineering contracts
[AGENT](./AGENT.md) · [SKILL](./SKILL.md) · [PROMPT](./PROMPT.md) · [TOOLING](./TOOLING.md) · [WORKFLOW](./WORKFLOW.md) · [RUNTIME](./RUNTIME.md)

**Status: NOT STARTED.** These are specific scientific and engineering proposals, not executable deployments, experimental findings or empirically verified strategies.
