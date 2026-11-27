# PLAN — Countercyclical Repo Haircut Adjustment with Hysteresis
**QMG-20261127-02 | A — Securities finance | US/EU non-cleared secured funding | proposal only**
## Architecture
Source adapter → vintage/rights registry → haircut-hysteresis-policy state builder → baseline → candidate → matched economic replay → independent gate. Grain: collateral class × legal agreement × risk day. Data: haircut vintages, eligible collateral marks, stress indicators, margin calls and realized liquidation outcomes. Timing: previously published volatility/rates, signed terms before risk decision.

## Model sequence
Baseline rolling volatility haircut with same mandatory floors; candidate hysteretic threshold controller; advanced robust stochastic policy with joint liquidation and funding shocks. Estimate on rolling training windows, tune only validation, freeze holdout and cost assumptions. Build a no-action comparator when capacity uncertain. Primary risk: selection by counterparty and tail scarcity; slower hikes may worsen credit losses. No private data in repo.

## Proposed typed functions
load(as_of, source_ids)->versioned_rows; state(rows, cutoff)->haircut-hysteresis-policy decision states; baseline(states)->actions; candidate(states, config)->actions; evaluate(actions, outcomes)->p99 incremental margin call, expected shortfall of closeout, floor breaches; validate() rejects mandatory floor jump; fast crash; prohibited haircut decrease. Map functions to REQ-001–004 and NFR-001/002; report missing inputs rather than fabricate. Illustrative $400m affected collateral; $120k annual avoided reserve carrying cost at assumed 3% on $4m lower reserve; no credit loss improvement assumed. Check actual costs/available liquidity before shadow. No implementation yet.
