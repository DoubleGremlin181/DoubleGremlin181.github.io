---
title: "Laundry Insights From Scraping 4000 Washer/Dryers in San Francisco"
layout: post
date: 2025-12-12 15:46
tag:
- python
- visualization
- data analytics
image: /assets/images/posts/san-francisco-laundry-analysis/washing-machine.png
headerImage: true
hidden: false
description: "San Francisco Laundry Analysis"
category: blog
author: kavishhukmani
externalLink: false
plotting: true
---

[↓ Jump to the Key Metrics & Plots](#key-metrics-and-plots)

A few months ago, I had the terrible misfortune of needing to house-hunt in San Francisco’s insanely competitive rental market. After weeks of getting beat out for every apartment I applied to, I finally found one where I wasn’t applicant #11. It was perfect and checked all my boxes except one: an in-unit washer/dryer.

The situation wasn’t the worst though. There was a large laundry room in the basement, and an app that shows the current status of every machine. That got my wheels spinning. Maybe I could figure out the laundry habits of a couple hundred of my new neighbors to avoid standing around waiting for someone else's cycle to end.

The app, [Wash Connect](https://www.wash.com/wash-connect/), requires you to sign-up for your specific laundry room by either via Bluetooth (while in proximity of the room) or using an eight digit location code. Once successfully signed up, you don’t need to be physically in the room to view the available machines.

I started poking around to see if they had a web app since that would make my life much easier. But alas, Android and iOS only. I went down the rabbit hole of intercepting traffic from an Android app and ended up with a rooted virtual device and HTTP Toolkit. Next, I created a burner account, found the APIs being called, and a few Claude prompts later, I had a scraper running on a Linode box.

I checked back in after a few days and everything was going better than expected, i.e., nothing broke. I also started looking at the code Claude wrote and noticed there was no authentication on the API! I was baffled that I had somehow missed that. I thought to myself, can I analyze laundry habits for the entire country?

While this was running, I spent the next few days were spent solving a different problem: how do I tie these laundry rooms to their addresses? While digging through the API responses, I found a few nuggets of information that could help. The room name field was the first line of the room’s address. I could easily verify this for my apartment. The other piece of the puzzle was that the first two digits of a location’s identifier represented the state code. I was still missing key details like the city and ZIP code, but I had enough to mostly piece things together. Pasting these two parts into Google usually identified the full address. I ended up using the [Google Maps Geocoding API](https://developers.google.com/maps/documentation/geocoding/requests-geocoding) to automate exactly this. It wasn't perfect, but it seemed good enough and was all I had.

I came back to my scraper a week later to find that my requests were suddenly failing. After some digging, I concluded that my box’s IP had been blocked, probably because it was generating a huge amount of traffic and someone noticed. Determined to finish a project I had gotten so far into, I decided to scale down. I spun up a new Linode box and filtered my scraper for only locations in San Francisco.

I left it running for the entire month of October. Here are the results.

## Key Metrics and Plots

• Wash Connect operates 451 laundry rooms in San Francisco with 2,095 washers and 2,023 dryers  
• Most Wash operated locations have fewer than 10 machines, likely condos and smaller apartments  
• While most rooms have a 1:1 W/D ratio, that’s not always the case. Additionally, Dryer usage is typically higher because the cycles run longer  
• Time of day matters far more than day of week. That being said, the peak laundry time is Sunday 11 a.m.

### Laundry Room Locations by Neighborhood

{% include plots/san-francisco-laundry-analysis/neighborhood_map.html %}

### Washer/Dryer Usage Trends

{% include plots/san-francisco-laundry-analysis/citywide_usage_timeseries.html %}

<br/>
<details>
<summary><b>Trends by Neighborhood (Click to expand)</b></summary>
{% include plots/san-francisco-laundry-analysis/neighborhood_usage_timeseries.html %}
</details>

### Laundry Room Size

{% include plots/san-francisco-laundry-analysis/machine_distribution_histogram.html %}

## Acknowledgments and Disclosures

Potential Safety Issue: The lack of authentication on this data means it could be misused if someone were so inclined. I contacted the Wash team to report this, and they told me they were already aware and had intentionally decided to keep the data publicly accessible.

Washing Machine Icon made by <a href="https://www.flaticon.com/authors/kosonicon" title="kosonicon"> kosonicon </a> from <a href="https://www.flaticon.com/" title="Flaticon">www.flaticon.com</a>