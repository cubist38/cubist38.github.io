---
layout: post
read_time: true
show_date: true
title: "Fundanmentals of Probability for Data Science illustrated with Python examples"
date: 2023-09-28
img: posts/2023-10-01-probability/thumbnail.webp
tags: [probability, data science]
category: theory
author: Gia-Huy Vuong
description: "This guide provides an introduction to Probability, a crucial concept in Data Science. To begin with, we will discuss about the basic topics of Probability, such as binomial distribution, central limit theorem, normal distribution, and Z-score. Each concept is explained in a simple, non-mathematical manner and illustrated with examples."
---
## Probability and its Significance
### What is the Probability?
Probability is a fundanmental concept in Data Science that quantifies the likelihood of an event or outcome. The probability of an event is always between 0 and 1. If the probability of an event is 0, it means that the event is impossible. On the other hand, if the probability of an event is 1, it means that the event is certain.

Life is inherently uncertain, with outcomes of various situations remaining unknown until they occur. Questions about weather, academic success, sports outcomes, and career advancements exemplify these uncertainties. These scenarios will be related to common terminologies used in our subsequent discussion:

- **Experiment**: refers to situations with uncertain outcomes, such as daily weather patterns.
- **Outcome**: is the result of a single instance of an experiment. For instance, if it is a sunny day, the outcome of today's weather experiment is "Sunny day"
- **Event**: is one or more outcome from an experiment. "Sunny day" is a possible event for the weather experiment.
- **Probability**: quantifies the likelihood of an event. If there’s a 80% chance of rain tomorrow, the probability of the outcome “Sunny day” for tomorrow’s weather experiment is 0.8.