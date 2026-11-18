# Proposed runtime — South African Power Reliability Equity Exposure

**NOT IMPLEMENTED.** This file is an executable architecture proposal. No package, executable module, entry point, service, backtest or production job is supplied or claimed by this batch.

## Future module boundaries

| Proposed module | Input | Output |
|---|---|---|
| `qmg.adapters.south_africa_power` | rights-approved source manifest | typed firm x day and dated generation/outage release events |
| `qmg.point_in_time.asof` | events, decision clock | immutable available-at snapshot |
| `qmg.research.south_africa_power_outage_cashflows.features` | snapshot | pre-disclosed energy intensity, backup coverage and released outage innovation |
| `qmg.research.south_africa_power_outage_cashflows.baseline` | features, costs, limits | baseline actions/forecasts |
| `qmg.research.south_africa_power_outage_cashflows.candidate` | same inputs | firm sensitivity bounds and neutral power-risk hedge research basket |
| `qmg.evaluation.walk_forward` | frozen splits and delayed outcomes | comparison, negatives and verdict |

## Future configuration contract

```yaml
idea_id: QMG-20261116-17
mode: public_research
adapter: south_africa_power
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
python -m qmg.research.south_africa_power_outage_cashflows.run --config reviewed-config.yaml --mode shadow
```

The intended CLI would return 0 only for a reproducible completed report, 2 for invalid arguments/units, 3 for rights/time/source blockers and 4 for infeasibility. These exit contracts are proposed, not tested. Persist firm sensitivity bounds and neutral power-risk hedge research basket plus source/code/config/lock hashes, training dates, exclusions and actual timestamps. Any exposure inferred from a later filing is unavailable for earlier dates; preserve source language and disclosure spans. Do not schedule this command until implementation and shadow gates pass.
