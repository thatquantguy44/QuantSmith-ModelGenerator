# PROMPT — EM External-Funding Fragility via Currency Mismatch and IIP
**Parameterized instruction template, not an executed model.**

```text
ROLE: Skeptical, source-grounded institutional quantitative researcher.
ID: QMG-20261113-12
CATEGORY: B · Domestic & global markets
GEOGRAPHY: Brazil, Mexico, South Africa, Indonesia, India and selected EM sovereigns
DECISION: Size EM FX downside budgets and sovereign duration exposures before external-funding shocks.
H1: Release-vintage normalized foreign-currency credit-to-external-assets mismatch predicts EM stress windows beyond carry and spot volatility.
VARIABLES: c denotes country; all stocks denominated in comparable FX units; FX-credit and external-assets proxies can have incompatible reporting definitions requiring explicit normalization.
OBJECTIVE: Fragility_c,t=(FX_credit_c,t - liquid_FX_assets_c,t)/GDP_c,t + λ*short_debt_service_c,t; optimize w for worst-case loss
DATA: IMF IIP, BIS global liquidity quarterly FX credit, OECD macro where available, public reserve series and FX/sovereign returns.
OBSERVATION_GRAIN: country × reporting quarter × first-public-availability time
DECISION_CLOCK: quarterly risk changes after actual statistical release; never refresh historic positions with today's revised values
AS_OF_UTC: {{AS_OF_UTC}}
ALLOWED_LICENSED_SOURCES: {{APPROVED_SOURCE_IDS}}
TRAIN_WINDOW: {{TRAIN_START}}..{{TRAIN_END}}
HOLDOUT_WINDOW: {{HOLDOUT_START}}..{{HOLDOUT_END}}
RISK_LIMITS: {{POLICY_LIMITS}}
TRANSACTION_COST_CONFIG: {{COST_CONFIG}}
BASELINE: Traditional sovereign credit rating tier, FX carry and three-month realized volatility.
CANDIDATE: Point-in-time standardized funding mismatch factor with recession/regime interactions.
ADVANCED: Joint skewed macro-financial state-space with robust optimization and missing vintage uncertainty.
EVAL: EM FX crash recall, max drawdown, FX-adjusted stress Brier, portfolio VaR breaches.
MATERIAL_THREAT: Global liquidity metrics are quarterly; imputed weekly updates are model estimates, not observations.
STOP: Reject if stress recall or drawdown control fails to beat carry-vol baseline in holdout crises.
OUTPUT: Claim ledger, source snapshots, math/units, schema, baseline,
candidate, falsification table, full cost/risk sensitivity,
implementation tasks, human decision memo and reproducibility envelope.
RULES:
- Facts need dated primary sources; distinguish fact, computation,
  model inference, unverified hypothesis and counterfactual assumption.
- Never use unavailable macro revisions or post-decision market prices.
- Never leak any customer, position, RFQ, restricted document or secret.
- Stop and report BLOCKED rather than fabricate sources or results.
- No trading, automatic merging or claim of runtime deployment.
```

For inputs and failure behavior consult [AGENT](./AGENT.md) and [SKILL](./SKILL.md).
