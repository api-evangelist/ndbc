# NDBC — National Data Buoy Center (ndbc)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

The NOAA National Data Buoy Center (NDBC) operates a global network of over 1,000 moored buoys, drifting buoys, Coastal-Marine Automated Network (C-MAN) stations, and partner stations that continuously measure and transmit meteorological and oceanographic conditions. Real-time and historical data — wind direction and speed, wave height and period, sea surface temperature, atmospheric pressure, air temperature, dew point, visibility, and salinity — are distributed freely via HTTP file URLs, a THREDDS/OPeNDAP server (NetCDF), an RSS observation feed, and a latest-observations snapshot updated every five minutes. No API key or authentication is required; data is in the public domain under U.S. government open-data policy.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/ndbc/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/ndbc/refs/heads/main/apis.yml)

## Scope

- **Position:** Consumer
- **Access:** 3rd-Party

## Tags

- NOAA
- Marine
- Buoys
- Ocean
- Weather
- Waves
- Meteorological
- Oceanographic
- Real-Time
- Historical
- Government
- Open Data

## Timestamps

- **Created:** 2026-06-13
- **Modified:** 2026-06-13

## APIs

### NDBC Real-Time Data Service

Provides access to the last 45 days of meteorological and oceanographic observations from NDBC moored buoys and C-MAN coastal stations. Data files are served via HTTPS at https://www.ndbc.noaa.gov/data/realtime2/ and named by station identifier and measurement type (e.g., 41002.txt for standard meteorology, 41002.spec for spectral wave summaries). Measurement types include standard meteorology (wind, pressure, temperature, waves), continuous winds, spectral wave data (summaries, raw energy density, directional components), ADCP currents, oceanographic parameters, and tide data. Most stations report hourly; data typically appears within 25 minutes after the hour. Missing values are represented as MM.

- **Human URL:** [https://www.ndbc.noaa.gov/faq/rt_data_access.shtml](https://www.ndbc.noaa.gov/faq/rt_data_access.shtml)
- **Base URL:** `https://www.ndbc.noaa.gov/data/realtime2`

#### Tags

- Real-Time
- Buoys
- Meteorological
- Oceanographic
- Waves
- Winds
- Temperature
- Pressure

#### Properties

- [Documentation](https://www.ndbc.noaa.gov/faq/rt_data_access.shtml)
- [Documentation](https://www.ndbc.noaa.gov/docs/ndbc_web_data_guide.pdf)
- [Documentation](https://www.ndbc.noaa.gov/faq/measdes.shtml)
- [Base U R L](https://www.ndbc.noaa.gov/data/realtime2/)

### NDBC Latest Observations Service

Delivers a consolidated snapshot of the most recent observation from every active NDBC and partner station, refreshed every five minutes. The flat text file at https://www.ndbc.noaa.gov/data/latest_obs/latest_obs.txt contains 23 columns (station ID, latitude, longitude, UTC timestamp, wind direction and speed, gust, wave height, dominant and average wave period, mean wave direction, atmospheric pressure, pressure tendency, air temperature, water temperature, dew point, visibility, and tide). Per-station RSS files and a geographic observation search RSS feed are also available. No authentication required.

- **Human URL:** [https://www.ndbc.noaa.gov/faq/rss_access.shtml](https://www.ndbc.noaa.gov/faq/rss_access.shtml)
- **Base URL:** `https://www.ndbc.noaa.gov/data/latest_obs`

#### Tags

- Latest Observations
- Real-Time
- All Stations
- RSS
- Snapshot

#### Properties

- [Documentation](https://www.ndbc.noaa.gov/faq/rss_access.shtml)
- [Base U R L](https://www.ndbc.noaa.gov/data/latest_obs/latest_obs.txt)
- [Base U R L](https://www.ndbc.noaa.gov/rss/ndbc_obs_search.php)

### NDBC Historical Archive Service

Provides quality-controlled historical observations from NDBC stations organized as annual files (prior years) and monthly files (current year) accessible at https://www.ndbc.noaa.gov/data/historical/. Measurement categories mirror the real-time service: standard meteorology, continuous winds, spectral wave data, ADCP currents, and oceanographic parameters. Data formats and column definitions are identical to the real-time files except that missing values use variable counts of nines (999, 9999, 99.0) rather than MM. A web-based historical observation search is available at histsearch.php and climatic summaries at climate.php.

- **Human URL:** [https://www.ndbc.noaa.gov/faq/archive.shtml](https://www.ndbc.noaa.gov/faq/archive.shtml)
- **Base URL:** `https://www.ndbc.noaa.gov/data/historical`

#### Tags

- Historical
- Archive
- Climate
- Quality-Controlled
- Annual
- Monthly

#### Properties

- [Documentation](https://www.ndbc.noaa.gov/faq/archive.shtml)
- [Documentation](https://www.ndbc.noaa.gov/faq/measdes.shtml)
- [Base U R L](https://www.ndbc.noaa.gov/data/historical/)
- [Documentation](https://www.ndbc.noaa.gov/histsearch.php)
- [Documentation](https://www.ndbc.noaa.gov/climate.php)

### NDBC THREDDS/OPeNDAP NetCDF Service

Exposes NDBC station time-series data as NetCDF files through a THREDDS Data Server (TDS) at https://dods.ndbc.noaa.gov/ using the OPeNDAP protocol. Dataset categories include standard meteorology (stdmet), continuous winds (cwind), spectral wave density (swden), acoustic Doppler current profiler (adcp, adcp2), oceanographic (ocean), water level (wlevel), DART tsunami (dart), and peak/mean currents (pwind, mmbcur). Files follow the naming pattern SSSSStYYYY.nc; real-time files use year 9999. An OceanSITES-format TAO buoy collection and HF Radar surface currents are also available via the same server.

- **Human URL:** [https://dods.ndbc.noaa.gov/](https://dods.ndbc.noaa.gov/)
- **Base URL:** `https://dods.ndbc.noaa.gov`

#### Tags

- NetCDF
- THREDDS
- OPeNDAP
- Scientific Data
- Currents
- Tsunami
- OceanSITES

#### Properties

- [Documentation](https://dods.ndbc.noaa.gov/)
- [Base U R L](https://dods.ndbc.noaa.gov/)
- [Documentation](https://dods.ndbc.noaa.gov/oceansites/)

### NDBC HF Radar Surface Currents Service

Provides near-real-time ocean surface current speeds and directions derived from High-Frequency (HF) radar systems operated by NDBC and partner networks in various nearshore areas of the United States. Both hourly and 25-hour averaged current products are available. The service is accessible at https://hfradar.ndbc.noaa.gov/ and integrates with the broader NDBC station data infrastructure. Data supports maritime safety, search and rescue operations, and coastal oceanographic research.

- **Human URL:** [https://hfradar.ndbc.noaa.gov/](https://hfradar.ndbc.noaa.gov/)
- **Base URL:** `https://hfradar.ndbc.noaa.gov`

#### Tags

- HF Radar
- Surface Currents
- Coastal
- Nearshore
- Real-Time

#### Properties

- [Documentation](https://hfradar.ndbc.noaa.gov/)
- [Base U R L](https://hfradar.ndbc.noaa.gov/)

## Common Properties

- [Portal](https://www.ndbc.noaa.gov/)
- [Documentation](https://www.ndbc.noaa.gov/docs/ndbc_web_data_guide.pdf)
- [Documentation](https://www.ndbc.noaa.gov/faq/rt_data_access.shtml)
- [Documentation](https://www.ndbc.noaa.gov/faq/measdes.shtml)
- [Documentation](https://www.ndbc.noaa.gov/faq/stations.shtml)
- [Contact](https://www.ndbc.noaa.gov/contacts.shtml)
- [Privacy Policy](https://www.noaa.gov/privacy-policy)
- [Terms of Service](https://www.noaa.gov/disclaimer)
- [Plans](/plans/free.md)
- [Rate Limits](/rate-limits/rate-limits.md)
- [Fin Ops](/finops/finops.md)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
