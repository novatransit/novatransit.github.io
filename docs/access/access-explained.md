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

## Why does access change?

If you've come from the [Access Dashboard](https://nvtc.maps.arcgis.com/apps/dashboards/3bda02cf9d8e4a39ae666dca202d8446), you might be wondering about how each of the variables on the sidebar affect access. In this section, we'll try to explain how and why each variable would affect your access.

### Travel time

Within a certain travel time, you can only go so far distance-wise - and the further you can go, the more opportunities you can reach. In the documentation of this project, we explain why we chose the [four travel time bands](/docs/access/parameters.md) of 30, 45, 60, and 90 minutes that we did - in general, each time band represents a different set of trips that one might want to take, but to put it here:

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

![Image explaining representative transit service patterns comparing peak to midday and pre and post pandemic](/assets/images/transit_service_patterns.png)

During midday hours, your access to opportunities like shopping, medical appointments, and social activities may be quite different depending on available transit service. Traditional peak-focused agencies often reduce service significantly during these hours. However, agencies that have adopted more distributed service patterns may actually provide better midday access than they did before the pandemic.

Evening service can greatly affect your access to entertainment, dining, and social opportunities. Many agencies reduce service frequency significantly after 9 PM, and some routes may stop running entirely. This can create a "transportation barrier" to evening activities, particularly for those who depend on transit. The availability of late-night service often determines whether you can participate in evening social and cultural opportunities without needing to rely on other modes.

### Jurisdiction

Finally, where you live and what land use affects your access just as much as the transportation options available to you - in fact, they often go hand in hand.

----

[^1]: These terms are fairly interchangeable when used in this context.

[^2]: This is the definition given by the [State Smart Transportation Initiative](https://ssti.us/measuring-accessibility/).

[^3]: Many agencies will also run Sunday service on federal or state holidays.

[^4]: Virginia Railway Express - a commuter railway service jointly run by NVTC and the Potomac-Rappahannock Transportation Commission (PRTC)