---
title: Access to Opportunity explained
parent: Access to Opportunity Analysis
nav_order: 2
layout: default
---
## What is Access?

Access to opportunity, also called *"access to destinations"* or *"accessibility"*, or just *access*[^1] is a way to measure how easily people can reach destinations. [^2] This "ease" is usually measured in travel time.

Another way to think of access is, as explained by *Human Transit* author Jarrett Walker, *your ability to go places so that you can do things*, which is further defined by a *[wall around your life](https://humantransit.org/basics-access-or-the-wall-around-your-life)*.

> Whoever you are, and wherever you are, there’s an area you could get to in an amount of time
> that’s available in your day. That limit defines a wall around your life.  Outside that wall
> are places you can’t work, places you can’t shop, schools you can’t attend, clubs you can’t 
> belong to, people you can’t hang out with, and a whole world of things you can’t do.

In short, access is your ability to get to places and the opportunities those places hold - which can include work, education, amenities, or any number of things.

## Why measure access?

We measure access because it provides a clear way of understanding how transportation and transportation investments affect the way that we live, work and play.

It also helps us understand how transportation is and isn't meeting our needs - and doesn't aim to make predictions (like traditional modeling does).

## How does the dashboard measure access?

We used a multi-step process to calculate and measure access - all of which is detailed further in the rest of the documentation of this project. The list below summarize some of the key steps needed to take to make this analysis happen.

1. Gather data on demographics (population, jobs, etc.)
2. Set an analysis area boundary
3. Generate a grid of hexagons of roughly-equivalent size within the boundary
4. Join the demographics data with the grid
5. Define two areas - origins (Northern Virginia) and destinations (Northern Virginia and the rest of the DC region)
6. Calculate transit travel times across multiple times of day and days of the week given the defined origin and destination areas.
7. Calculate the number of opportunities reachable from each hex to all hexes up to certain travel time thresholds.
8. Weight these opportunities reachable against population and other demographics factors.
9. Get number of opportunities accessible within *X* number of minutes at *Y* time of day on *Z* day of week.

## Why does access change?

If you've come from the [Access Dashboard](https://nvtc.maps.arcgis.com/apps/dashboards/3bda02cf9d8e4a39ae666dca202d8446), you might be wondering about how each of the variables on the sidebar affect access. In this section, we'll try to explain how and why each variable would affect access.

### Travel time

Within a certain travel time, you can only go so far distance-wise - and the further you can go, the more opportunities you can reach. In the documentation of this project, we explain why we chose the [four travel time bands](/docs/access/parameters.html) of 30, 45, 60, and 90 minutes that we did - in general, each time band represents a different set of trips that one might want to take, but to put it here:

> * **30 minutes** - Local trips within immediate communities
> * **45 minutes** - Medium-distance trips to major employment centers  
> * **60 minutes** - Longer commutes that still represent reasonable transit travel times
> * **90 minutes** - Long-distance commutes from the farthest reaches of the region, often made using commuter bus services

It also represents a different amount of opportunities available to you within that set amount of time - the longer you have (or are willing) to travel, the more opportunities you might have.

### Day of week

In Northern Virginia, our transit agencies, like most in North America, typically run three types of schedules:

* Weekday schedules (with the most service)
* Saturday schedules (usually with less service than weekday, but more than Sunday - oftentimes more in the later hours of the night)
* Sunday schedules (usually with the least amount of service)[^3]

Some agencies, such as VRE[^4], only run service at peak times - which means they only run service on weekdays. Other agencies with a large concentration of commuter-oriented services have similar setups, where they may have a large portion of their service only running during weekdays or have increased frequencies during weekdays.

Therefore, depending on the day of week, your access might increase simply based on the fact that you might have more service available to you on a weekday (either a route being present or a route being more frequent). Conversely, on a Saturday or Sunday, your access to opportunities may be more limited due to reduced transit service.

### Time of trip start

Like differences between days of the week, transit agencies often have different amounts of service depending on the time of day.

Most agencies offer the most transit service during "peak hours" (6am to 9am in the morning and 3pm to 6pm in the evening). Some agencies also provide extra service during both peak times and in the peak direction of travel.

In the context of the DC metropolitan area, peak period/peak direction service is typically service that goes towards areas like DC, the Pentagon, and the Rosslyn/Ballston Corridor in the morning and away from those areas in the evening.

This type of peak-focused scheduling was standard for most agencies before the pandemic (and still is for many agencies, especially those operating commuter-focused services).

However, owing to changes in work patterns emerging from the pandemic, many agencies shifted from peak-focused service to service that distributed it throughout the day, often with a focus on the midday period.


During midday hours, your access to opportunities like shopping, medical appointments, and social activities may be quite different depending on available transit service. Traditional peak-focused agencies often reduce service significantly during these hours. However, agencies that have adopted more distributed service patterns may actually provide better midday access than they did before the pandemic.

Evening service can greatly affect your access to entertainment, dining, and social opportunities. Many agencies reduce service frequency significantly after 9 PM, and some routes may stop running entirely. This can create a "transportation barrier" to evening activities, particularly for those who depend on transit. The availability of late-night service often determines whether you can participate in evening social and cultural opportunities without needing to rely on other modes.

### Jurisdiction

It's often said that *[the best transportation plan is a good land use plan](https://ssti.us/2025/07/16/the-best-transit-plan-is-a-strong-land-use-plan/)*. Where you live affects access just as much as the transit service that's available to you - in fact, they often go hand in hand.

There are many factors of land use and the built environment that can influence demand for transit. A good summary of these six factors comes from TransLink in Vancouver, British Columbia, who in their [Transit Service Guidelines](https://www.translink.ca/-/media/translink/documents/plans-and-projects/managing-the-transit-network/transit-oriented-communities/transit-services-guidelines-public-summary.pdf) call them the "6 D's of Transit-Oriented Community Design." To paraphrase them, they are:

* **Destinations:** Coordination between land use and transportation, which provides places for people to go to
* **Distance:** A well-connected street network that encourages walking and makes it easy to connect with transit service
* **Design:** Places built with multimodal travel in mind and provide a safe, comfortable, and enjoyable public realm
* **Density:** Concentrating growth and activity near high-frequency transit
* **Diversity:** A mix of land uses to offer a variety of opportunities
* **Demand management:** Strategies applied to promote the use of modes like walking, cycling and transit.

You can see these factors in action in certain areas of the map even before selecting by jurisdiction. In areas of Northern Virginia that are:

* relatively dense,
* have a variety of activity types,  
* are generally designed with a walkable and connected street grid and
* are on or near high-frequency transit service,

Access is much higher. Examples of places like this include the Rosslyn-Ballston corridor, Pentagon City/Crystal City, Old Town Alexandria, and neighborhoods throughout the region anchored by a Metrorail station.

Conversely, areas that are:

* less dense,
* have fewer activity types (i.e. only have housing or only have offices),
* have a disconnected street grid that's harder to walk in and
* are farther away from high-frequency transit service

have lower levels of access.

Jurisdictions that have more of the former kind of land use tend to have higher levels of access, while jurisdictions with the latter kind of land use have lower levels of access. However, it's not always evenly distributed across each jurisdiction, which is why we show both a map with details of jobs reachable and statistics calculated for each jurisdiction.

----

[^1]: These terms are fairly interchangeable when used in this context.

[^2]: This is the definition given by the [State Smart Transportation Initiative](https://ssti.us/measuring-accessibility/).

[^3]: Many agencies will also run Sunday service on federal or state holidays.

[^4]: Virginia Railway Express - a commuter railway service jointly run by NVTC and the Potomac-Rappahannock Transportation Commission (PRTC)