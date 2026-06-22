# ClinicalTrials.gov — Prosthetic Trial Analysis

## Data Collection Notes

The ClinicalTrials.gov API tools encountered schema validation issues during data collection (the `query` and `filter` parameters require specific internal property names that were not documented in the tool schema). Automated trial retrieval was not successful.

## Recommended Query Strategy

To retrieve prosthetic-related clinical trials:

- **Condition**: "prosthetic" OR "prosthesis" OR "amputation" OR "limb prosthesis"
- **Intervention**: "prosthetic training", "socket design", "osseointegration"
- **Filter by**: "Open" studies, US locations (WV, KY, MS, TN, AL, LA)

## Analysis Dimensions

### By Trial Status
| Status | Expected Insights |
|--------|------------------|
| Recruiting | Active opportunities for patient enrollment |
| Not yet recruiting | Upcoming studies to watch |
| Completed | Results that may inform practice |
| Suspended/Withdrawn | Gaps in research continuity |

### By Region (US States)
West Virginia (WV), Kentucky (KY), Mississippi (MS), Tennessee (TN), Alabama (AL), Louisiana (LA)

### By Phase
- Phase 1/2: Early-device safety and efficacy
- Phase 3: Pivotal effectiveness trials
- Phase 4: Post-market surveillance and optimization

## Expected Findings

1. **Geographic concentration**: Most prosthetic trials are concentrated in major academic medical centers
2. **Rural gap**: Very few trials target rural populations or include rural delivery models
3. **Condition focus**: Upper-limb prosthetics and osseointegration are overrepresented; lower-limb and pediatric prosthetics are underrepresented
4. **Payment/research gap**: States like WV, KY, and MS have fewer industry-sponsored trials

## How to Ingest Full Data

```bash
curl "https://clinicaltrials.gov/api/v2/studies?query.term=prosthetic&filter.status=OPEN&pageSize=1000"
```