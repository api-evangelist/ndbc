# NDBC API FinOps

## Cost Model

NDBC data services are **free of charge**. They are funded by the U.S. federal government through NOAA and provided as a public service under the principles of open government data. There are no usage fees, subscription tiers, per-request charges, data licensing fees, or overage costs.

## No Authentication Required

No API key purchase, account registration, credit card, or payment of any kind is needed to access NDBC data. All services — real-time file access, the latest observations snapshot, historical archives, THREDDS/NetCDF, RSS feeds, and HF Radar — are fully open.

## Open Data Policy

NDBC data is released under the U.S. government open data policy. All observations and derived products are in the public domain and may be used freely for commercial, research, operational, or personal purposes without licensing fees. Attribution to NOAA NDBC is encouraged but not legally required for U.S. government works.

## Cost Drivers for Consumers

While NOAA does not charge for data access, organizations integrating NDBC data into applications may incur their own infrastructure costs:

| Cost Category | Notes |
|---------------|-------|
| Compute | ETL jobs, data pipelines, or real-time ingestion applications |
| Storage | Caching or archiving observations and historical files |
| Egress | Cloud data transfer costs if calling NDBC services from a cloud-hosted workload |
| Engineering | Development and ongoing maintenance of integrations |
| Monitoring | Alerting and observability for data pipelines ingesting real-time feeds |

## Budget Recommendations

- **No budget allocation is needed for NDBC data access itself.**
- For high-volume historical data needs, use THREDDS/NetCDF bulk download rather than fetching individual text files to minimize egress and compute costs.
- Cache the consolidated latest observations file (`/data/latest_obs/latest_obs.txt`) rather than polling individual station files to reduce per-request overhead.
- Budget engineering time for handling missing-value codes (MM in real-time, variable 9-series in historical) and parsing fixed-width space-delimited text formats.

## References

- NDBC Web Data Guide: https://www.ndbc.noaa.gov/docs/ndbc_web_data_guide.pdf
- NOAA Open Data Dissemination: https://www.noaa.gov/information-technology/open-data-dissemination
- NOAA Privacy Policy: https://www.noaa.gov/privacy-policy
- NOAA Disclaimer: https://www.noaa.gov/disclaimer
