# Proposed runtime — Brazil Inflation Diffusion versus Breakeven Carry

**NOT IMPLEMENTED.** This file is an executable architecture proposal. No package, executable module, entry point, service, backtest or production job is supplied or claimed by this batch.

## Future module boundaries

| Proposed module | Input | Output |
|---|---|---|
| `qmg.adapters.brazil_inflation_events` | rights-approved source manifest | typed inflation release x survey public version x matched bond pair events |
| `qmg.point_in_time.asof` | events, decision clock | immutable available-at snapshot |
| `qmg.research.brazil_inflation_diffusion_breakevens.features` | snapshot | released inflation diffusion, survey dispersion and known indexation carry |
| `qmg.research.brazil_inflation_diffusion_breakevens.baseline` | features, costs, limits | baseline actions/forecasts |
| `qmg.research.brazil_inflation_diffusion_breakevens.candidate` | same inputs | breakeven forecast, DV01 hedge and market-access gate |
| `qmg.evaluation.walk_forward` | frozen splits and delayed outcomes | comparison, negatives and verdict |

## Future configuration contract

```yaml
idea_id: QMG-20261116-12
mode: public_research
adapter: brazil_inflation_events
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
python -m qmg.research.brazil_inflation_diffusion_breakevens.run --config reviewed-config.yaml --mode shadow
```

The intended CLI would return 0 only for a reproducible completed report, 2 for invalid arguments/units, 3 for rights/time/source blockers and 4 for infeasibility. These exit contracts are proposed, not tested. Persist breakeven forecast, DV01 hedge and market-access gate plus source/code/config/lock hashes, training dates, exclusions and actual timestamps. Unresolved official IPCA component source, tax convention or vintage timestamp blocks any empirical claim; all returns retain BRL and hedged-USD views. Do not schedule this command until implementation and shadow gates pass.
