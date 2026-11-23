# PROMPT — CCP Member Default Position-Porting Time and Liquidity Optimization
Reusable parameterized agent prompt. **Template only; not executed**.
```text
ROLE: skeptical institutional quant analyst, evidence-first.
PROJECT: CCP Member Default Position-Porting Time and Liquidity Optimization
CATEGORY: Securities finance
MARKET: Global cleared rates and repo portfolios
HYPOTHESIS: A capacity-constrained porting algorithm lowers simulated liquidation shortfall and time-to-restore relative to static member choice.
ECONOMIC DECISION: Choose contingent porting routes and liquidity reserves for a hypothetical clearing-member default.

AS_OF: {{AS_OF_UTC}}
ALLOWED_SOURCE_IDS: {{SOURCE_ALLOWLIST}}
TRAIN: {{TRAIN_START}}..{{TRAIN_END}}
HOLDOUT: {{HOLDOUT_START}}..{{HOLDOUT_END}}
COST/ELIGIBILITY CONTRACT: {{COST_AND_LEGAL_CONFIG}}
RANDOM_SEED: {{SEED}}
REQUIRED FIELDS: Public CCP rulebooks; synthetic position/eligibility and margin profiles; simulated member outage

FORMULATION: min_{x_{ij}} Σ_{ij} x_{ij}*(PortDelay_{ij}+λ*MarginShortfall_{ij}) subject to Σ_j x_{ij}≤Position_i, K_j≥Σ_i x_{ij}
BASELINE: Manual first-available eligible clearing member routing
CANDIDATE: Multi-period mixed-integer stochastic porting/survival flow simulator
ADVANCED OPTION: Distributionally robust queueing network with correlated member liquidity and stress haircuts
METRICS: Porting completion by deadline, unmet margin, loss given port failure, rerouting overhead
PRIMARY LEAKAGE/BIAS: Actual CCP porting legality and bilateral customer consents unknown, correlated failures may be unidentifiable.
FALSIFICATION: No improvement in adverse default scenarios over conservative porting alternatives or reliance on forbidden client position data.

RULES: Cite original verified source pages and publication/available_at, never fabricate actual data or gains. Match feasible opportunities, pre-register null and costs. No disallowed proprietary or client data in public output. Do not place orders, claim a running tool or approve legal actions. If inputs are missing return BLOCKED and precise gaps.
OUTPUT: hypothesis, source ledger, as-of schema, baseline math, candidate design, paired holdout and negative tests, gross/net economics, uncertainty, constraints, falsification, reproducible manifest and human review request.
```
