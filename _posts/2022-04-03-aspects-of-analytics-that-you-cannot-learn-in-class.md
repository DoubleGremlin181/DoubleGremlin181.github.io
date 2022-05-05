---
title: "Aspects of Analytics That You Cannot Learn In Class"
layout: post
date: 2022-04-03 23:59
tag:
- essay
- coursework
headerImage: false
description: "Essay on practical aspects of analytics"
category: blog
author: kavishhukmani
externalLink: false
---

<span class="evidence">This blog was initially written as part of my coursework for BAX 462 - Practicum Elaboration at UC Davis.</span>

![Header Image](/assets/images/posts/aspects-of-analytics-that-you-cannot-learn-in-class/image1.jpeg)

<figcaption class="caption">Photo by Markus Winkler on Unsplash</figcaption>

<br>

## Analytics is hard.

It is not something that can be taught entirely through a textbook. Of course, that is not to say that the classes I took as part of my master’s degree were not effective. They ensured that I understood the theory and thought process behind every process while also giving me a hands-on experience through projects and assignments. However, they do not provide any training on certain aspects related to the scale and complexity of real-world projects.

This is where my year-long practicum came in to picture. For the uninitiated, a [practicum](https://www.merriam-webster.com/dictionary/practicum), as defined by Merriam-Webster, is a course of study [..] that involves the supervised practical application of previously studied theory. The MS in Business Analytics program at UC Davis consists of a year-long practicum, a critical factor in my decision to join the program. The goal of the practicum is to provide real-world experience in analytics by working on real projects in a team at an external organization.

---

In this blog, I will be talking about six practical aspects of implementing analytics that I learned through the practicum. While some of these topics are mentioned in various courses, their elaborate nature is hard to gauge. To this end, I will also provide ways that you, the reader, can gain these skills (or at least get a better understanding of them). I shall refer to this as the <i>Best Alternative to a Practicum Experience</i>, or <i>BATPE</i> for short.

## 1. Dealing with multiple sources of data

While Kaggle datasets might be fantastic for someone new to analytics, they are not representative of working in the industry. Most companies have their data spread across multiple tables, data warehouses, and types of databases. It is common to join multiple tables at different levels of data, each with its own intricacies. This requires a combination of domain knowledge as well as SQL expertise to ensure correct and quick execution. During my practicum, I learned this lesson the hard way when our team ran some inefficient joins, which hogged all the resources, making the database inaccessible to anyone else.

<b>BATPE:</b> Work on an analytics project with multiple related data sources. Since finding a curated dataset in this format is hard, you would have to use multiple public datasets and even scrape your own data. My advice would be to choose a topic revolving around geographic or demographic differences as fields such as <i>County</i> and <i>Gender</i> are present in many diverse datasets which are publically available.

## 2. Dealing with dirty data

Although this is a topic often covered in courses, it is glossed over as it is time-consuming to try out practically. While most larger companies have Data Engineering teams that deal with data cleaning, it is still an important skill to have for an analyst, especially as one should know the ins and outs of the data before performing any analysis.

<b>BATPE:</b> This might be the easiest of my learnings to replicate as there are quite a few dirty datasets available. It is common to find incomplete information in government-released information. I would recommend [Australian Marriage Law Postal Survey, 2017](https://www.abs.gov.au/ausstats/abs@.nsf/mf/1800.0), and [NYCs 311 Service Requests from 2010 to Present](https://data.cityofnewyork.us/Social-Services/311-Service-Requests-from-2010-to-Present/erm2-nwe9) if you are looking for a challenge. Another option would be to scrape some data yourself.

## 3. Experiment tracking and collaboration

While group projects provide some exposure to the collaborative nature of working in a team, they are seldom as structured as working in a well-oiled team at a job. They also do not emphasize tracking and versioning models and datasets.

<b>BATPE:</b> Maintaining a proper Git repository for the code while following best practices can drastically reduce the friction of collaboration in university or boot camp group projects. [Weights & Biases](https://wandb.ai/site) is another incredible tool that helps with experiment tracking, dataset versioning, and model management.

## 4. Model runtime

There are two aspects to a model’s runtime- training time and execution/prediction time. Both of these might or might not be significant based on the use case. The importance of training time depends on how long it takes and how regularly the model is updated, whereas prediction time might be critical when dealing with streaming data.

<b>BATPE:</b> Monitor times while creating models. A few tips from my experience would be to use scalable and parallelizable frameworks and algorithms such as Dask or PySpark instead of Pandas and LightGBM instead of XGBoost. Another common trick is to drop excess data and precision, trading off some accuracy for better performance.

## 5. Model deployment

An ML project does not end with computing the F1-Score on the test set. Deployment is a vital part of the analytics life cycle, without which nobody would be able to use the incredibly beneficial models you built. During my practicum, I deployed the models my team built on Azure and exposed them through a REST API to run nightly batch processes. While this is not very complicated, it is important to know the pros and cons of different kinds of deployments to ensure that the model is being run without any hiccups or manual intervention.

<b>BATPE:</b> There are some high-quality online resources, such as [this blog by StackOverflow](https://stackoverflow.blog/2020/10/12/how-to-put-machine-learning-models-into-production/) and [this course by DeepLearning.AI](https://www.coursera.org/learn/deploying-machine-learning-models-in-production) which provide an in-depth look into deployments and the world of MLOps.

## 6. Performance tracking

Deployment is also not the end of an ML project. It is critical to monitor the model inputs and KPIs for drift to detect any external changes affecting the model’s performance. This ensures that the model has not worsened over time, causing it to provide negative business value.

<b>BATPE:</b> Neptune.ai has a beautiful [guide](https://neptune.ai/blog/how-to-monitor-your-models-in-production-guide) that dives deep into monitoring models in production.

## Bonus: Timelining

Creating a timeline for any sort of work is hard. Even experienced professionals often misjudge the time needed to solve a problem. People often overestimate the efficiency and do not factor in complexities that might arise mid-way through a project. While there is no BATPE for this, working on more projects helps you get a better grasp on estimating deadlines. In accordance with [Hofstadter’s law](https://en.wikipedia.org/wiki/Hofstadter%27s_law), a common rule of thumb is to double any initial estimate.

---

### Not impressed?

Is there any aspect that you think that I should have mentioned? Or a BATPE that you recommend? Feel free to tweet at me.

<a href="https://twitter.com/intent/tweet?screen_name=2gremlin181&ref_src=twsrc%5Etfw" class="twitter-mention-button" data-show-count="false">Tweet at @2gremlin181</a><script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>


---
