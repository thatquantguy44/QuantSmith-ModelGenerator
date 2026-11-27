# PLAN — Global Pension Contribution-Aware Rebalancing with Trading Frictions
**QMG-20261127-20 | B — Domestic/global markets | US, UK, Canada and Netherlands institutional allocation | proposal only**
## Architecture
Source adapter → vintage/rights registry → pension-cashflow-rebalance state builder → baseline → candidate → matched economic replay → independent gate. Grain: plan type × asset class × month / public annual country aggregates. Data: policy weights, cash contributions/benefits, portfolio NAV, returns and executable costs. Timing: only annual OECD releases for long-run calibration; approved plan cashflows known before month-end decisions.

## Model sequence
Baseline calendar rebalancing with identical cashflow forecast and policy constraints; candidate convex no-trade-band optimizer; advanced multi-period stochastic control using uncertain benefit payments. Estimate on rolling training windows, tune only validation, freeze holdout and cost assumptions. Build a no-action comparator when capacity uncertain. Primary risk: OECD aggregates cannot reveal real plan trades; benefit schedules private. No private data in repo.

## Proposed typed functions
load(as_of, source_ids)->versioned_rows; state(rows, cutoff)->pension-cashflow-rebalance decision states; baseline(states)->actions; candidate(states, config)->actions; evaluate(actions, outcomes)->net transaction costs, tracking error, liquidity shortfalls, turnover; validate() rejects cash outflow shock, policy band breach, zero liquidity, stale NAV. Map functions to REQ-001–004 and NFR-001/002; report missing inputs rather than fabricate. $500m illustrative portfolio × 2 bps annual net turnover savings=$100k/year; no trading strategy alpha. Check actual costs/available liquidity before shadow. No implementation yet.
