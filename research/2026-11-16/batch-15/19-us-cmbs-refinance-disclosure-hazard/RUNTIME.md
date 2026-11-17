# Proposed runtime — US CMBS Refinance Hazard from Public Disclosures

**NOT IMPLEMENTED.** This file is an executable architecture proposal. No package, executable module, entry point, service, backtest or production job is supplied or claimed by this batch.

## Future module boundaries

| Proposed module | Input | Output |
|---|---|---|
| `qmg.adapters.cmbs_public_vintages` | rights-approved source manifest | typed loan x public reporting vintage x maturity/outcome event events |
| `qmg.point_in_time.asof` | events, decision clock | immutable available-at snapshot |
| `qmg.research.us_cmbs_refinance_disclosure_hazard.features` | snapshot | public refinance cash gap, maturity hazard and amendment lineage |
| `qmg.research.us_cmbs_refinance_disclosure_hazard.baseline` | features, costs, limits | baseline actions/forecasts |
| `qmg.research.us_cmbs_refinance_disclosure_hazard.candidate` | same inputs | competing-outcome probabilities, missing-field coverage and tranche mapping limits |
| `qmg.evaluation.walk_forward` | frozen splits and delayed outcomes | comparison, negatives and verdict |

## Future configuration contract

```yaml
idea_id: QMG-20261116-19
mode: public_research
adapter: cmbs_public_vintages
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
python -m qmg.research.us_cmbs_refinance_disclosure_hazard.run --config reviewed-config.yaml --mode shadow
```

The intended CLI would return 0 only for a reproducible completed report, 2 for invalid arguments/units, 3 for rights/time/source blockers and 4 for infeasibility. These exit contracts are proposed, not tested. Persist competing-outcome probabilities, missing-field coverage and tranche mapping limits plus source/code/config/lock hashes, training dates, exclusions and actual timestamps. Require filing accession and field-level source path; unparsed or contradictory outcome definitions fail closed for that loan. Do not schedule this command until implementation and shadow gates pass.
