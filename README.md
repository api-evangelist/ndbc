# NDBC — National Data Buoy Center (ndbc)

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
