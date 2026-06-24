---
title: "Worldcupmaxxing ⚽️"
layout: post
date: 2026-06-24 12:00
tag:
- essay
- optimization
- sports
image: /assets/images/posts/worldcupmaxxing/header.jpg
headerImage: true
projects: false
hidden: false
description: "How many 2026 World Cup matches could a single person actually attend?"
category: blog
author: kavishhukmani
externalLink: false
mathjax: false
plotting: false
---

If you've been following the FIFA World Cup, it might seem like Gianni Infantino is at every match. That got me wondering:

How many 2026 World Cup matches could a single person actually attend in person?

With matches spread across 16 cities in 3 countries, this quickly turned into a surprisingly fun optimization problem.

I pulled the full tournament schedule, modeled travel times between host cities (both by private jet and motorcade), and added constraints for stadium entry/exit, airport transfers, and immigration processing.

From there, I formulated it as an LP to find the maximum feasible number of matches one person could attend.

The answer: **49 matches**.

![Optimal World Cup 2026 attendance route](/assets/images/posts/worldcupmaxxing/anim_vip.gif)

For comparison, Gianni Infantino attended every match of the 2022 World Cup in Qatar. But with the 2026 tournament spread across North America, even FIFA-president-level logistics only gets you to 49 of the 104 matches.
