# NDBC API Rate Limits

## Overview

NDBC does not publish hard numeric rate limits (requests per second, per minute, or per day). However, NDBC explicitly requests that users limit their retrievals to a minimal, courteous level. Excessive automated polling can degrade service for all users and may result in temporary IP-level access restrictions.

## Published Guidance

From the NDBC Web Data Guide and real-time data access FAQ:

> "Limit your retrievals to a minimal level."

Most stations report hourly, and data is generally available within 25 minutes after the top of the hour. There is no benefit to polling more frequently than the station reporting interval.

## Best Practices

- **Poll no more than once per hour** for real-time station data files; data does not change more frequently.
- **Use the latest observations file** (`/data/latest_obs/latest_obs.txt`) for bulk station snapshots — it consolidates all station observations into one file, refreshed every 5 minutes, rather than fetching individual station files.
- **Fetch data ranges efficiently**: retrieve as much data as needed in each request rather than making many small requests.
- **Cache responses locally** when the same data will be consumed multiple times.
- **Use THREDDS/NetCDF access** for bulk or historical data retrieval rather than fetching individual text files in a loop.
- **Identify your application** with a descriptive User-Agent string so NDBC staff can contact you if your access pattern causes issues.

## Data Update Frequencies

| Data Source | Update Frequency |
|-------------|-----------------|
| Individual station real-time files | Hourly (within ~25 min after the hour) |
| Latest observations file (latest_obs.txt) | Every 5 minutes |
| RSS observation feeds | Every 5 minutes (TTL: 5 minutes) |
| Historical archive files | Monthly (current year) / Annually (prior years) |
| THREDDS NetCDF real-time files | Hourly |

## Authentication

No API key, token, or account registration is required. All NDBC data services are fully open and publicly accessible.

## Throttling Behavior

NDBC has not published specific throttle thresholds. Users experiencing access issues or needing high-volume data access should contact:

- webmaster.ndbc@noaa.gov
- https://www.ndbc.noaa.gov/contacts.shtml
