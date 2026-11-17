# Proposed runtime — Treasury Futures Delivery Inventory Reservation

**NOT IMPLEMENTED.** This file is an executable architecture proposal. No package, executable module, entry point, service, backtest or production job is supplied or claimed by this batch.

## Future module boundaries

| Proposed module | Input | Output |
|---|---|---|
| `qmg.adapters.treasury_delivery` | rights-approved source manifest | typed CUSIP x futures contract x observation timestamp events |
| `qmg.point_in_time.asof` | events, decision clock | immutable available-at snapshot |
| `qmg.research.futures_delivery_inventory_reservation.features` | snapshot | invoice value, basket eligibility and marginal delivery option shadow cost |
| `qmg.research.futures_delivery_inventory_reservation.baseline` | features, costs, limits | baseline actions/forecasts |
| `qmg.research.futures_delivery_inventory_reservation.candidate` | same inputs | lendable face limits and delivery-feasibility certificate |
| `qmg.evaluation.walk_forward` | frozen splits and delayed outcomes | comparison, negatives and verdict |

## Future configuration contract

```yaml
idea_id: QMG-20261116-04
mode: public_research
adapter: treasury_delivery
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
python -m qmg.research.futures_delivery_inventory_reservation.run --config reviewed-config.yaml --mode shadow
```

The intended CLI would return 0 only for a reproducible completed report, 2 for invalid arguments/units, 3 for rights/time/source blockers and 4 for infeasibility. These exit contracts are proposed, not tested. Persist lendable face limits and delivery-feasibility certificate plus source/code/config/lock hashes, training dates, exclusions and actual timestamps. Contract units, invoice rounding and delivery rules must be versioned and independently reconciled before optimization. Do not schedule this command until implementation and shadow gates pass.
