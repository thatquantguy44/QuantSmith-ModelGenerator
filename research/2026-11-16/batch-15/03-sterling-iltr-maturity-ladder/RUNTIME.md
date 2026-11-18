# Proposed runtime — Sterling ILTR Auction Demand Smoothing

**NOT IMPLEMENTED.** This file is an executable architecture proposal. No package, executable module, entry point, service, backtest or production job is supplied or claimed by this batch.

## Future module boundaries

| Proposed module | Input | Output |
|---|---|---|
| `qmg.adapters.boe_iltr` | rights-approved source manifest | typed auction x collateral set x release version events |
| `qmg.point_in_time.asof` | events, decision clock | immutable available-at snapshot |
| `qmg.research.sterling_iltr_maturity_ladder.features` | snapshot | clearing-spread intervals, reserve coverage and maturity bucket exposure |
| `qmg.research.sterling_iltr_maturity_ladder.baseline` | features, costs, limits | baseline actions/forecasts |
| `qmg.research.sterling_iltr_maturity_ladder.candidate` | same inputs | auction cash-demand ladder with allocation sensitivity bounds |
| `qmg.evaluation.walk_forward` | frozen splits and delayed outcomes | comparison, negatives and verdict |

## Future configuration contract

```yaml
idea_id: QMG-20261116-03
mode: public_research
adapter: boe_iltr
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
python -m qmg.research.sterling_iltr_maturity_ladder.run --config reviewed-config.yaml --mode shadow
```

The intended CLI would return 0 only for a reproducible completed report, 2 for invalid arguments/units, 3 for rights/time/source blockers and 4 for infeasibility. These exit contracts are proposed, not tested. Persist auction cash-demand ladder with allocation sensitivity bounds plus source/code/config/lock hashes, training dates, exclusions and actual timestamps. Every schedule uses Europe/London DST and verified effective facility calibration; missing auction rule version blocks recommendation. Do not schedule this command until implementation and shadow gates pass.
