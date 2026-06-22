# Data Sources & Methodology

## ClinicalTrials.gov Data
- **Source**: National Library of Medicine / ClinicalTrials.gov
- **API**: clinicaltrialsgov-mcp-server
- **Note**: Schema issues prevented full automated retrieval; manual retrieval recommended
- **Query**: `curl "https://clinicaltrials.gov/api/v2/studies?query.term=prosthetic&filter.status=OPEN&pageSize=1000"`

## Geographic & Provider Data
- **Geocoding**: OpenStreetMap Nominatim (via OSM MCP server)
- **Locations**: WV (38.48°N, 80.84°W), EKY (37.25°N, 83.20°W), MS Delta (34.00°N, 90.20°W)
- **Provider Mapping**: OSM health/amenity category search within 50km radius
- **Limitations**: OSM may be incomplete for rural areas

## Demographic Data
- **Sources**: HRSA Area Health Resources Files, US Census Bureau
- **Rural classification**: RUCA codes and HRSA designations

## Verification Needed
- [ ] Provider licensure lists from WV, KY, MS Boards of Prosthetics/Orthotics
- [ ] Active ClinicalTrials.gov studies with prosthetic conditions
- [ ] HRSA-designated MUAs and HPSAs
- [ ] Local providers not captured in OSM