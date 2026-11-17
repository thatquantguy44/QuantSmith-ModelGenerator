# Proposed runtime — India Bond Index-Flow Saturation

**NOT IMPLEMENTED.** This file is an executable architecture proposal. No package, executable module, entry point, service, backtest or production job is supplied or claimed by this batch.

## Future module boundaries

| Proposed module | Input | Output |
|---|---|---|
| `qmg.adapters.india_index_events` | rights-approved source manifest | typed government bond x announcement/rebalance cohort x public flow release events |
| `qmg.point_in_time.asof` | events, decision clock | immutable available-at snapshot |
| `qmg.research.india_index_flow_duration_neutral.features` | snapshot | announced flow pressure, free-float turnover and lagged foreign ownership saturation |
| `qmg.research.india_index_flow_duration_neutral.baseline` | features, costs, limits | baseline actions/forecasts |
| `qmg.research.india_index_flow_duration_neutral.candidate` | same inputs | event-study estimands, placebo diagnostics and duration-neutral research basket |
| `qmg.evaluation.walk_forward` | frozen splits and delayed outcomes | comparison, negatives and verdict |

## Future configuration contract

```yaml
idea_id: QMG-20261116-14
mode: public_research
adapter: india_index_events
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
python -m qmg.research.india_index_flow_duration_neutral.run --config reviewed-config.yaml --mode shadow
```

The intended CLI would return 0 only for a reproducible completed report, 2 for invalid arguments/units, 3 for rights/time/source blockers and 4 for infeasibility. These exit contracts are proposed, not tested. Persist event-study estimands, placebo diagnostics and duration-neutral research basket plus source/code/config/lock hashes, training dates, exclusions and actual timestamps. Announced and effective membership must occupy separate columns; unknown original announcement time blocks that cohort. Do not schedule this command until implementation and shadow gates pass.
