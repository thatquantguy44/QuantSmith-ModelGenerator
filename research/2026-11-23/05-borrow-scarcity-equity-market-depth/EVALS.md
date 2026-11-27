# EVALS — Borrow Scarcity Causal Effect on Equity Market-Maker Quoted Depth
**No empirical test run. Evaluation design, not evidence.**

## H1/H0 and economics
H1: Exogenous changes to borrow supply lower subsequent displayed depth/increase effective spreads more than matched control stocks.
H0: the feasible `Spread/depth forecasting using only realized volatility and market cap` benchmark is not improved net of risk/cost.
Candidate: `Matched differences-in-differences/event-time instrumental analysis`. Advanced: Structural market-maker inventory equilibrium with dynamic borrowing constraint
Metrics: Event-time β confidence interval, placebos, effective spread, depth and incremental risk price.

## Mandatory synthetic invariants
- `available_at_utc <= decision_time`, calendar/session alignment and source-version hash.
- Feasible decision constraints match: Depth_{i,t}=α_i+δ_t+β*BorrowSupplyShock_{i,t}+γ'X_{i,t}+ε_{i,t}; H0: β=0.
- Units and payable/receivable cash direction from: BorrowSupplyShock is preannounced/exogenous eligible inventory change; X contains liquidity and issuer controls.
- True negative controls: Selection on distressed shorts, simultaneous volatility and hard-to-borrow endogenous events.
- Equal event/asset universe, quoted bid/ask, capacity and no-action alternatives.

## Empirical design if licensed data eventually approved
Time-blocked train/validation/holdout, embargo overlaps and original-vintage release lags. Conduct matched policy replay, bootstrap by independent event block, monitor false discoveries across multiple choices, expose failed dates and liquidity drawdowns.
**Stop:** No pre-registered effect with valid pretrends/instruments or effect only on illiquid untradeable names..

## Cost and publication
Not an unconditional trading signal; capacity depends on quote depth and borrow clearance, include adverse selection.
$220k assumed total 24m development/data/maintenance cost; assumed launch in month 9; assumed annual gross outcome downside/base/upside $0k/$120k/$310k. Resulting 24m net ROI **-100.0% / -31.8% / 76.1% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
Public papers and official datasets are context only, not replication. Any material positive result requires independently reproduced code + signed human review; no automatic trading.

## Acceptance gating
AC-001..AC-005 from SPEC each requires a runnable test record and model/data rights signoff. If source is incomplete, report a negative or blocked result, not a proxy alpha claim.
