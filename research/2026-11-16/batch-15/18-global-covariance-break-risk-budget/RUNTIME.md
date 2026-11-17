# Proposed runtime — Global Covariance-Break Risk-Budget Controller

**NOT IMPLEMENTED.** This file is an executable architecture proposal. No package, executable module, entry point, service, backtest or production job is supplied or claimed by this batch.

## Future module boundaries

| Proposed module | Input | Output |
|---|---|---|
| `qmg.adapters.global_session_returns` | rights-approved source manifest | typed instrument x completed local session x common information cutoff events |
| `qmg.point_in_time.asof` | events, decision clock | immutable available-at snapshot |
| `qmg.research.global_covariance_break_risk_budget.features` | snapshot | lag-aware covariance, break statistic and marginal turnover cost |
| `qmg.research.global_covariance_break_risk_budget.baseline` | features, costs, limits | baseline actions/forecasts |
| `qmg.research.global_covariance_break_risk_budget.candidate` | same inputs | hold/rebalance research decision, risk-contribution certificate and stale-session report |
| `qmg.evaluation.walk_forward` | frozen splits and delayed outcomes | comparison, negatives and verdict |

## Future configuration contract

```yaml
idea_id: QMG-20261116-18
mode: public_research
adapter: global_session_returns
as_of_utc: REQUIRED_FROM_RUN
source_manifest: REQUIRED_REVIEWED_PATH_AND_HASH
cost_config: REQUIRED_MEASURED_OR_LABELED_SCENARIO
limits: REQUIRED_DOMAIN_APPROVED_LIMITS
seed: 20261116
allow_private_inputs: false
allow_live_orders: false
```

Illustrative **future** command, expected to fail today because no runtime exists:

```bash
python -m qmg.research.global_covariance_break_risk_budget.run --config reviewed-config.yaml --mode shadow
```

The intended CLI would return 0 only for a reproducible completed report, 2 for invalid arguments/units, 3 for rights/time/source blockers and 4 for infeasibility. These exit contracts are proposed, not tested. Persist hold/rebalance research decision, risk-contribution certificate and stale-session report plus source/code/config/lock hashes, training dates, exclusions and actual timestamps. All returns carry local session end and actual receive time; no forward fill across a market closure without a stale flag. Do not schedule this command until implementation and shadow gates pass.
