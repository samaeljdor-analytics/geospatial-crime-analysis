Geospatial Crime Hotspot Analysis — Chicago

Spatial analysis identifying crime hostpot in Chicago using QGIS

A kernel density estimation (KDE) heatmap identifying crime hotspots in Chicago, built in QGIS from the city's public crime data.

Data
Source: City of Chicago Data Portal — Crimes 2001 to Present
https://data.cityofchicago.org/Public-Safety/Crimes-2001-to-Present/ijzp-q8t2/about_data
Sample: ~20,000 reported incidents from a recent multi-month window
Fields used: incident date, primary crime type, latitude/longitude


Method
1. Loaded the incident CSV into QGIS as a point layer (WGS 84 / EPSG:4326)
2. Reprojected to NAD83 / UTM Zone 16N (EPSG:26916) so density could be calculated in real-world meters rather than degrees
3. Ran Kernel Density Estimation with a 500m search radius and 50m output resolution
4. Styled the result with a sequential color ramp (light → dark red) to highlight relative density
5. Layered an OpenStreetMap basemap underneath for geographic context


Result
Darker areas indicate a higher concentration of reported incidents within the search radius; lighter areas indicate fewer.

Findings
1. Density is not evenly distributed — it concentrates most heavily along major road corridors and around the central/downtown area, consistent with higher foot and vehicle traffic in those zones
2. The single strongest hotspot centers on Chicago's Loop / River North area, near the confluence of the Chicago River branches (approx. 41.89°N, -87.63°W) — consistent with the area's high density of foot traffic, retail, and transit
3. Density drops off noticeably toward the outer suburbs within this dataset's coverage area

Tools
QGIS · Kernel Density Estimation (Heatmap) · CSV/Delimited Text layers · Coordinate reference system reprojection

Notes / limitations
This sample reflects reported incidents only, not verified or adjudicated ones, per the source dataset's own disclaimer
A 500m radius and 50m resolution were chosen for a readable citywide view; a smaller radius would reveal more localized detail at the cost of a noisier map
