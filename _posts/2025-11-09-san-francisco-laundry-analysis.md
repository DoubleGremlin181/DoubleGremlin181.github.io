---
title: "Laundry Insights From Scraping 4000 Washer/Dryers in San Francisco"
layout: post
date: 2025-11-15 17:00
tag:
- python
- visualization
- data analytics
image: /assets/images/posts/san-francisco-laundry-analysis/washing-machine.png
headerImage: true
hidden: true
description: "San Francisco Laundry Analysis"
category: blog
author: kavishhukmani
externalLink: false
plotting: true
---

[Jump to the plots](#plots)

A few months ago, I had the terrible misfortune of needing to house-hunt in San Francisco’s insanely competitive rental market. After weeks of getting beat out for every apartment I applied to, I finally got one where I wasn’t applicant #11. It was perfect and checked all my boxes except one: an in-unit washer/dryer.

The situation wasn’t the worst though. There was a huge laundry room in the basement, and the app shows you the current status of every machine. That got my wheels spinning. Maybe I could figure out the laundry habits of a couple hundred of my new neighbors to avoid having to stand around waiting for someone else's cycle to end.

The app, [Wash Connect](https://www.wash.com/wash-connect/), uses Bluetooth during sign-in to figure out which laundry room you’re in, but after this initial setup, you don’t need to be physically near the room.

I started poking around to see if they had a web app since that would make my life much easier. But alas, Android and iOS only. I went down the rabbit hole of intercepting traffic from an Android app and ended up with a rooted virtual device and HTTP Toolkit.

All that remained was to log into my laundry room somehow and I’d be off to the races. Around that time, I noticed a Wash Connect instructions poster hanging in the laundry room. It mentioned a location code that can be used to log in without Bluetooth. Perfect! I created a burner account, found the APIs being called, and a few Claude calls later had a scraper running on a Linode box.

I checked on it after a few days and everything was going better than expected, i.e., nothing broke. I also started looking at the code Claude wrote and noticed there was no authentication for the API. I was baffled that I somehow missed that. I though to myself, can I analyze laundry habits for the entire country?

Everything had gone better than I could have imagined so far, given that half my projects hit a roadblock halfway. Fueled by this optimism, I vibe-coded an “update” (essentially a rewrite) to my scraper to find all 15,000+ laundry rooms and scrape them. I pushed run and called it a night.

The next few days were spent solving a different problem: how do I tie these laundry rooms to their addresses? While digging through the API responses, I noticed a few nuggets of information that could help. The room name field was the first line of the room’s address. I could easily verify this for my apartment. The other piece of the puzzle was that the first two digits of a location’s identifier were the state code. I was still missing key details like the city and ZIP code, but I had enough to mostly piece things together. Pasting these two parts into Google usually identified the full address. I ended up using the [Google Maps Geocoding API](https://developers.google.com/maps/documentation/geocoding/requests-geocoding) to automate exactly this. It wouldn’t be perfect, but it seemed good enough and was all I had.

I came back to my scraper a week later to find that my requests were suddenly failing. That was weird, since the app still worked fine. I concluded that my box’s IP had been blocked, probably because it was generating a huge amount of traffic and someone noticed.

Determined to finish a project I had gotten so far into, I decided to scale down. I spun up a new Linode box and filtered my scraper for only locations in San Francisco.

I left it running for the entire month of October. Here are a few key metrics from the data:

• Wash Connect operates 451 laundry rooms in San Francisco with 2,095 washers and 2,023 dryers  
• Most Wash operated locations have fewer than 10 machines, likely condos and smaller apartments  
• While most rooms have a 1:1 W/D ratio, that’s not always the case, Additionally Dryer usage is higher since cycles run longer  
• Time of day matters far more than day of week. That being said, the peak laundry time is Sunday 11 a.m.  

You can browse some of these insights in the charts below or find all the data on my [GitHub](https://github.com/DoubleGremlin181/Wash-Connect-Analysis) to explore trends for your own laundry room.

## Plots

### Laundry Room Locations By Neighborhood

{% include plots/san-francisco-laundry-analysis/neighborhood_map.html %}

### Washer/Dryer Usage Trends

{% include plots/san-francisco-laundry-analysis/citywide_usage_timeseries.html %}

<br/>
<details>
<summary>Trends By Neighborhood (Click to expand)</summary>
{% include plots/san-francisco-laundry-analysis/neighborhood_usage_timeseries.html %}
</details>

### Laundry Room Size

{% include plots/san-francisco-laundry-analysis/machine_distribution_histogram.html %}



Washing Machine Icon made by <a href="https://www.flaticon.com/authors/kosonicon" title="kosonicon"> kosonicon </a> from <a href="https://www.flaticon.com/" title="Flaticon">www.flaticon.com</a>
