## Subscriber Mobility Analysis using Call Detail Records (CDR)

This is an analysis of mobility patterns derived from Call Detail Records (CDR) across various administrative regions. 
This study investigates the spatial distribution of cell towers and subscriber movement patterns, providing insights into aggregate mobility trends. 
The analysis includes aggregating subscriber counts, constructing mobility indicators, and detecting shifts due to significant events, potentially useful for telecommunications planning, urban mobility studies, and emergency response analysis.

### Data Overview:
Two main datasets were utilized:

CDR Data: Contains records of subscriber call activities, identified by unique subscriber IDs (msisdn) and location IDs.
Administrative Boundaries: Geographic boundaries for administrative regions, enabling spatial mapping and aggregation.

### Methodology and Analysis Steps:

* Cell Tower Mapping and Spatial Join :

Using Geopandas, cell towers were mapped across administrative boundaries to visualize distribution. A spatial join was conducted to associate each cell tower with an administrative region, enabling further locality-based aggregation.
* Subscriber Count Aggregation:

Aggregate 1: Computed daily unique subscriber counts across the entire region, setting a baseline for analyzing overall activity trends.
Aggregate 2: Calculated daily unique subscriber counts per locality. Only results with at least 15 unique subscribers were retained to ensure statistical relevance.
Analysis of Aggregates: Aggregate 2 counts were summed to compare with Aggregate 1, revealing differences due to overlapping subscriber presence across multiple localities. This discrepancy underscores that mobility data is not strictly additive across localities.

* Mobility Indicator Construction:

Baseline Establishment: To account for pre-event mobility, a baseline reference was constructed using a 7-day median of scaled subscriber counts leading up to January 14, 2016. This median reflects typical activity levels before notable changes.
Daily Scaled Subscriber Count: Each day’s subscriber count per locality was scaled relative to the baseline, generating a “percentage change from baseline” mobility indicator. This enabled tracking significant shifts in subscriber presence over time.
Trend Analysis:

By plotting daily subscriber counts per locality, an abrupt shift in mobility around January 14, 2016, was identified. This shift suggests a notable event that likely impacted subscriber behavior, such as increased travel or concentration in specific areas. These patterns could be attributed to public events, infrastructure disruptions, or other external factors affecting movement.

* Further Explorations and Findings:

Distinct Towers Visited per Subscriber: Analysis revealed the average and maximum number of unique towers visited by individual subscribers, highlighting habitual mobility ranges.
Distinct Administrative Regions Visited: On average, each subscriber visited multiple administrative regions, which supports observations of inter-locality mobility.
Daily Events per Subscriber: For each subscriber, an average daily count of call events was calculated, providing insight into engagement levels with the cellular network.
Hourly Activity Trends: Hourly call activity revealed peak and low periods, offering potential for time-based demand management.
* Conclusion: 
The analysis of CDR data has successfully provided a detailed view of subscriber mobility patterns, particularly in response to notable events. By aggregating data at both regional and daily levels, we constructed a robust mobility indicator that reflects baseline deviations and identified shifts in subscriber behavior. The spatial visualization of cell towers and region-based aggregations demonstrates how localized and overall mobility data can complement each other to paint a clearer picture of movement dynamics.
