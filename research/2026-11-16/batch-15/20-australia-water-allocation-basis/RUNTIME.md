# Proposed runtime — Australian Water Allocation Shadow Price and Crop Basis

**NOT IMPLEMENTED.** This file is an executable architecture proposal. No package, executable module, entry point, service, backtest or production job is supplied or claimed by this batch.

## Future module boundaries

| Proposed module | Input | Output |
|---|---|---|
| `qmg.adapters.australia_water_market` | rights-approved source manifest | typed water zone x allocation release x reported trade and crop season events |
| `qmg.point_in_time.asof` | events, decision clock | immutable available-at snapshot |
| `qmg.research.australia_water_allocation_basis.features` | snapshot | announced allocation innovation, transfer-zone shadow price and crop-water budget |
| `qmg.research.australia_water_allocation_basis.baseline` | features, costs, limits | baseline actions/forecasts |
| `qmg.research.australia_water_allocation_basis.candidate` | same inputs | crop-margin scenario, local water shadow price and hedge-basis feasibility verdict |
| `qmg.evaluation.walk_forward` | frozen splits and delayed outcomes | comparison, negatives and verdict |

## Future configuration contract

```yaml
idea_id: QMG-20261116-20
mode: public_research
adapter: australia_water_market
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
python -m qmg.research.australia_water_allocation_basis.run --config reviewed-config.yaml --mode shadow
```

The intended CLI would return 0 only for a reproducible completed report, 2 for invalid arguments/units, 3 for rights/time/source blockers and 4 for infeasibility. These exit contracts are proposed, not tested. Persist crop-margin scenario, local water shadow price and hedge-basis feasibility verdict plus source/code/config/lock hashes, training dates, exclusions and actual timestamps. Separate entitlement from allocation units and record ML, hectares and currency explicitly; unknown zone connectivity blocks cross-zone flow. Do not schedule this command until implementation and shadow gates pass.
