# Proposed runtime — Cross-Border Settlement Calendar Bridge Planner

**NOT IMPLEMENTED.** This file is an executable architecture proposal. No package, executable module, entry point, service, backtest or production job is supplied or claimed by this batch.

## Future module boundaries

| Proposed module | Input | Output |
|---|---|---|
| `qmg.adapters.settlement_calendars` | rights-approved source manifest | typed obligation leg x settlement service x UTC instant events |
| `qmg.point_in_time.asof` | events, decision clock | immutable available-at snapshot |
| `qmg.research.cross_border_calendar_bridge.features` | snapshot | service open intervals, version effective dates, cash-day gaps and DST conversion |
| `qmg.research.cross_border_calendar_bridge.baseline` | features, costs, limits | baseline actions/forecasts |
| `qmg.research.cross_border_calendar_bridge.candidate` | same inputs | prefunding dates, minimal cash bridge and infeasible-leg alerts |
| `qmg.evaluation.walk_forward` | frozen splits and delayed outcomes | comparison, negatives and verdict |

## Future configuration contract

```yaml
idea_id: QMG-20261116-08
mode: public_research
adapter: settlement_calendars
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
python -m qmg.research.cross_border_calendar_bridge.run --config reviewed-config.yaml --mode shadow
```

The intended CLI would return 0 only for a reproducible completed report, 2 for invalid arguments/units, 3 for rights/time/source blockers and 4 for infeasibility. These exit contracts are proposed, not tested. Persist prefunding dates, minimal cash bridge and infeasible-leg alerts plus source/code/config/lock hashes, training dates, exclusions and actual timestamps. Timezone-aware UTC storage with local service timezone preserved; unknown calendar version returns BLOCKED, never a guessed weekday. Do not schedule this command until implementation and shadow gates pass.
