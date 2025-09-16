---
title: Methodologies
parent: Dashboard
nav_order: 2
layout: default
---
## Methodologies

### Proximity to Transit Analysis

This analysis, originally on the Access to Transit tab of the dashboard, is really a proximity analysis. To learn more about the Access to Opportunity analysis and dashboard, you can find it [here](https://github.com/novatransit/nova-transit-access).

The Proximity to Transit analysis tells us how *close* people are to transit.

1. "Close" to bus is defined as within 1/4 mile from a bus stop.
2. "Close" to rail is defined as within 1/2 mile from a rail stop.
3. "Close" to commuter rail is defined as within 1 mile from a commuter rail stop.
4. "Close" to paratransit is defined as within 3/4 mile from a fixed-route, as required by the [Federal Transit Administration](https://www.transit.dot.gov/complementary-paratransit-service-does-requirement-paratransit-service-be-provided-within-three).

The step-by-step process for calcualting proximity to transit is as follows:

1. Plot transit stops (from GTFS data) as points
2. Create buffer around stops
   a. 1/4 mile for bus stops
   b. 1/2 mile for rail
   c. 1 mile for commuter rail
   d. 3/4 mile for paratransit
3. Join buffers together if:
   a. Estimating populations at a transit system level
   b. Estimating populations at a route level
4. Use spatially weighted areal interpolation to estimate the number of people from the census data who might fall within the transit buffers.

Note that this a rudimentary methodolgy for prxoimity to transit. This analysis:

1. Uses buffers that don't take into account the road network.
2. Assumes indiviudals are spread evenly among a geographic area.
3. Does not account for transit service operation. Proximity to a transit stop does not necessarily mean proximity to a transit service at all times of day.
