---
title: Analysis tools and configuration
parent: Access to Opportunity Analysis
nav_order: 5
layout: default
---
## Analysis tools, techniques, and configurations

As part of our NoVA Transit Dashboard refresh, NVTC sought out to redefine our access to transit and access to jobs methodology used in the dashboard. This document will cover the analysis tools and configuration for those tools used in the Access to Opportunity analysis.

The Access to Opportunity analysis measures how many jobs and destinations residents can reach using public transit within specific time limits. The core research question driving this analysis is: "How many jobs can a resident of Northern Virginia reach on a given day of the week at a specific time of day within a certain travel time using transit?"

## Tools used

### R5

This analysis, at its core, is built on the [R5 routing engine](https://github.com/conveyal/r5), an open-source routing engine library that aims to create realistic travel calculations for trips based on departure times from within a travel time window, which mirrors how people actually plan out their trips.

Specifically, this analysis is built on [R5r](https://ipeagit.github.io/r5r/), which is an implementation of R5 for the R language.

We use R5 to develop many-to-many travel time matrices that are then fed into custom functions that measure the number of opportunities reachable based on [certain defined parameters](/documentation/parameters.md).

R5-based analyses of access to opportunity have been used by public institutions, private sector organizations, and even by government agencies, such as in the Statistics Canada [Spatial Access Measures](https://www150.statcan.gc.ca/n1/pub/27-26-0001/272600012023001-eng.htm). Locally, a commercial implementation of R5 called [Conveyal Analysis](https://conveyal.com/) was used in WMATA's Better Bus Network Redesign to create a comparative dashboard between the then-existing network and the proposed redesigned network.

### Other tools

This analysis uses a number of other open-source tools within the R universe, namely those to work with geographic objects and data tables. Examples of these may be found in the [scripts](/scripts/) directory.

### Custom functions

To measure the access to opportunities, we use a custom function that measures cumulative access to opportunities within a certain travel cost cutoff (with the travel cost being time in minutes). This is similar to a generic cumulative cutoff function like that implemented in the [accessibility R package](https://ipeagit.github.io/accessibility/index.html).

## Analysis configuration

### Travel time matrix

As mentioned earlier, this analysis is built off of a travel time matrix generated in R using the R5r package. A number of variables are defined and constant for all analyses, which are listed below:

```r
mode <-c("WALK","TRANSIT") # Each trip can include both walking and transit segments
max_walk_dist <- 1609 #meters, roughly 1 mile
max_walk_time <- 30 #minutes
max_trip_duration <- 300 #minutes, roughly 5 hours
draws_per_minute <- 4 #how many simulations for each minute (for frequency-based GTFS files only)
```

The parameters for the travel time matrix itself are listed below:

```r
travel_time_matrix(r5r_network = r5r_network,
    origins = origin, # universe: centroids of hexes within the NVTC district
    destinations = dest, # universe: centroids of hexes within the DC metro area
    mode = mode, # as defined above
    departure_datetime = departure_datetime, # a time/date object based off the days and times defined in parameters
    percentiles = c(10,25,50,75,90), # travel time variability - see https://docs.conveyal.com/analysis/methodology#accounting-for-variability
    time_window = 60, # the window of time the analysis will sample trips from - for example, for a 7am departure time it will sample trips from 7 to 8
    max_walk_time  = max_walk_time,
    draws_per_minute = draws_per_minute, # how many simulations of each minute to run
    max_trip_duration = max_trip_duration,
    verbose = FALSE)
```

We iterate through generating a travel time matrix for each combination of travel time limit/day of week/time of day.

### Accessibility calculation

After running the travel time matrix, we then combine the travel time matrices for each scenario and calculate the access measures from that. We do this using the 50th percentile of the travel time as that tends to represent the most accurate depiction of trips and can cover edge cases in trips. This is the same approach that [Conveyal uses](https://docs.conveyal.com/analysis/methodology#accounting-for-variability) in their commercial product.[^1]

### Accessibility statistics

Finally, we generate a variety of accessibility statistics based on the accessibility layer. These statistics are not based on the raw "reachable" numbers, but rather population weighted averages. By weighting these values based on population or another demographic value, we are able to more accurately assess how many opportunities each subgroup is able to access.

We generate two types of statistics - one for the entire region and one for each jurisdiction in the NVTC district.[^2]

----

[^1]: For more information on this approach see Conway, Matthew Wigginton, Andrew Byrd, and Marco van der Linden (2017). [“Evidence-Based Transit and Land Use Sketch Planning Using Interactive Accessibility Methods on Combined Schedule and Headway-Based Networks.”](http://trrjournalonline.trb.org/doi/abs/10.3141/2653-06)
[^2]: The NVTC district is defined as Arlington, Fairfax, and Loudoun counties and the cities of Alexandria, Fairfax, and Falls Church.
