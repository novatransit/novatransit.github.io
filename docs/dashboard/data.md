---
title: Data sources
parent: Dashboard
nav_order: 1
layout: default
---
## Data sources for dashboard

The dashboard uses DRPT ridership and service data, GTFS, Census data, and MWCOG Employment estimates. Each data type is described in detail below.

### Virginia Department of Rail and Public Transportation (DRPT) Ridership and Service data

DRPT collects monthly data from transit providers in Virginia including Unlinked Passenger Trips (UPT), Vehicle Revenue Hours (VRH) and Vehicle Revenue Miles (VRM). Definitions for these three metrics are below. All three metrics are reported for every transit mode including bus, paratransit, commuter rail, and heavy rail. Data is only available from July 2018 onwards, the beginning of Virginia’s fiscal year 2019.

**Unlinked Passenger Trips (UPT):** Number of passengers who board public transportation vehicles, regardless of whether a passenger is transferring from another transit vehicle.

**Vehicle Revenue Hours (VRH):** Hours traveled by revenue vehicles (buses, vans, railcars, etc.) while in revenue service. 

**Vehicle Revenue Miles (VRM):** Miles traveled by revenue vehicles while in revenue service. 

DRPT requires transit agencies provide backup documentation to support all reported metrics. DRPT program managers formally review and validate these data using this documentation at least once a year. Program managers also perform ad hoc reviews of performance data on an as-needed basis as part of their quarterly grant meetings with transit agencies.

#### General Transit Feed Specification (GTFS)

Originally developed by Google, GTFS  is a standard data format for transit schedules. Transit agencies use GTFS to feed scheduled data into applications like Google Maps, Apple Maps and transit apps. The data include everything that is needed to know when and where transit will be available, including the specific location of transit stops, the timing and sequence of transit trips, the number of trips for each transit route and the days of the week each transit route operates. 

### Census Data

American Community Survey (ACS) 5-year estimates were used wherever census data was needed. 5-year estimates represent data collected over a period of time, in this case, five years. These data provide population, demographic, household, and commuting data across the United States. There are two primary advantages to using ACS 5-year estimates over other data sources:

1. “The primary advantage of using multiyear estimates is the increased statistical reliability of the data for less populated areas and small population subgroups.”
2. Data is available more frequently than Decennial Census data which is only collected every ten years

Although the data is available more frequently than Decennial Census data, the five-year range of the estimate means that year-over-year trends are not observable. This means it is not possible to observe differences between 2019 and 2020, for example. ACS 1-year estimates have this capability but these estimates are not suitable for smaller geographic areas, including City of Fairfax and City of Falls Church. As ACS 1-year estimates exclude two of NVTC’s jurisdictions, they are not appropriate in most cases for NVTC.

Data was procured from multiple different data tables . Some variables (e.g., total zero car households) were not readily available in existing tables and had to be calculated.

The calculations were all performed at the census tract level. Although more granular data is available, the census tract level was chosen due to the large number of calculations performed for this dashboard and the faster running time census tract calculations offer compared to finer geographic scales.

The following table details the census tables used. 


|     Variable                                 |     Census   Table             |     Definition                                                                               |   
|----------------------------------------------|--------------------------------|----------------------------------------------------------------------------------------------|
|     Total Population                         |     B01003 001                 |     Total Population                                                                         |
|     Total Commuters                          |     B08301 001                 |     Means Of Transportation To Work: Total                                                   | 
|     Total Transit Commuters                  |     B08301 010                 |     Means Of Transportation To Work: Public Transportation (Excluding Taxicab)             | 
|     Poverty Ratio Total                      |     C17002 001                 |     Ratio of Income to Poverty Level in the Past 12 Months: Total                          |   
|     Poverty Ratio Over 200 percent           |     C17002 008                 |     Ratio of Income   to Poverty Level in the Past 12 Months: 2.00 and Over                  |   
|     Poverty Ratio Under 200 percent          |     C17002 001 - C17002 008    |     Poverty Ratio Over 200 percent subtracted from Poverty Ratio Total                     |   
|     Zero car households (rental occupied)    |     B25044 008                 |     Tenure by Vehicles Available: Renter Occupied: No Vehicle Available                    |   
|     Zero car households (owner occupied)     |     B25044 003                 |     Tenure by Vehicles Available: Owner Occupied: No Vehicle Available                     |   
|     Total zero car households                |     B25044 003 + B25044 008    |     Zero car households (rental occupied) added to Zero car households (owner occupied)    |   
|     White population                         |     B02001 002                 |     Race: White Alone                                                                        |   
|     Non-white population                     |     B01003 001 - B02001 002    |     White Population subtracted from Total Population                                        |   

#### Metropolitan Washington Council of Governments (MWCOG) Employment Data

Part of MWCOG’s work includes forecasting population, employment and households in the greater Washington, DC region, including NVTC jurisdictions. MWCOG provides regional employment estimates for small geographic areas called transportation analysis zones (TAZs). MWCOG Round 9.2 Cooperative Forecasting 2020 Employment estimates were used for all calculations. 