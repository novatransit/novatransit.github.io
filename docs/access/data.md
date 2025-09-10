---
title: Data sources
parent: Access to Opportunity Analysis
nav_order: 3
layout: default
---
As part of our NoVA Transit Dashboard refresh, NVTC sought out to redefine our access to transit and access to jobs methodology used in the dashboard. This document will cover the sources of our data.

The access to opportunity analysis requires three main types of data: demographic information (population and jobs), transit service schedules, and geographic data for routing. Each source provides a specific piece of the puzzle for understanding how many opportunities residents can reach by transit.

## Demographics data

Demographics data comes from two sources: the Metropolitan Washington Council of Governments (MWCOG) Cooperative Forecasts and the US Census Bureau's American Community Survey (ACS) and Longitudinal Employer-Household Dynamics (LEHD) datasets.

### MWCOG data

MWCOG data forms the basis of our base population and jobs dataset, although MWCOG does ultimately source its data from Census data as well. We use MWCOG data because it captures the unique jobs environment of the DC metropolitan area—namely the high concentration of federal and military jobs—that LEHD datasets do not accurately represent due to federal reporting restrictions.

The specific layer from MWCOG is [available here.](https://rtdc-mwcog.opendata.arcgis.com/datasets/9b51789be2f14f51af089acd019dc2f9_0/explore?location=38.870038%2C-77.233464%2C8.68)

The specific field used is the 2025 population (POP2025) and employment (EMP2025) forecast.

### Census data

We use census data to provide additional information on demographic subgroups that are typically more dependent on transit access. These groups include:

* minority residents
* low-income residents
* transit commuters
* zero-vehicle households

The specific Census variables we collect are:

* **Total Population** (B01003_001)
* **Total Commuters** (B08301_001)
* **Public Transit Commuters** (B08301_010)
* **Household Count** (B25044_001)
* **Total Population for Poverty Status** (C17002_001)
* **Population Above 200% Poverty Level** (C17002_008)
* **Owner-Occupied Households with No Vehicle** (B25044_003)
* **Renter-Occupied Households with No Vehicle** (B25044_010)
* **White Population** (B02001_002)

We also collect LEHD jobs data with these parameters:

* **Data Type**: Workplace Area Characteristics (wac)
* **Job Type**: All jobs (JT01) 
* **Worker Segment**: All workers (S000)

This dataset is collected at the block group level but is not currently used in the analysis due to federal employment reporting limitations in the DC metro area.

Census data is collected at the block group level (small geographic areas of about 600-3,000 people used by the Census Bureau).

## Aggregation to hexes

Both demographic layers are then aggregated from the Transportation Analysis Zone (TAZ) and block group layers to a hex layer. Specifically, we use hexes generated from the [H3 grid system](https://h3geo.org), which is an open-source discrete global grid system for indexing geographies into a hexagonal grid. Hexagons provide more uniform spatial analysis than squares or other shapes, and the H3 system allows us to scale the grid size as needed for different analyses.

## Transit data

Transit data is collected from multiple agencies to capture the complete transit network available to Northern Virginia residents.

**Local NVTC region agencies:**

* Arlington Transit (ART)
* DASH (Alexandria)
* City-University-Everyone (CUE - Fairfax City)
* Fairfax Connector
* Loudoun County Transit (LCT)

**Regional transit agencies:**

* Washington Metropolitan Area Transportation Authority (WMATA) - both bus and rail
* Virginia Railway Express (VRE)
* Potomac-Rappahannock Transportation Commission/OmniRide

We use the most recent General Transit Feed Specification (GTFS) static files for each agency. GTFS is a standardized format that includes transit schedules, stop locations, and route information. For Northern Virginia agencies, the majority of this data is available through the Virginia Department of Rail and Public Transportation [(DRPT) GTFS clearinghouse](https://drpt.virginia.gov/data/gtfs-feed-clearinghouse/), while the WMATA GTFS is pulled from the [WMATA Developer Portal](https://developer.wmata.com).

## Map data

Map data is generated using exports from OpenStreetMap. The exports include the routable street network (roads accessible to pedestrians and vehicles) and dedicated footpaths for walking connections between transit stops.
