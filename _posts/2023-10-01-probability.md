---
layout: post
read_time: true
show_date: true
Mathjax: yes
title: "Fundanmentals of Probability for Data Science illustrated with Python examples"
date: 2023-09-28
img: posts/2023-10-01-probability/thumbnail.webp
tags: [probability, data science]
category: theory
author: Gia-Huy Vuong
description: "This guide provides an introduction to Probability, a crucial concept in Data Science. To begin with, we will discuss about the basic topics of Probability, such as binomial distribution, central limit theorem, normal distribution, and Z-score. Each concept is explained in a simple, non-mathematical manner and illustrated with examples."
---
## Overview
This guide provides an introduction to Probability, a crucial concept in Data Science. To begin with, we will discuss about the basic topics of Probability, such as binomial distribution, central limit theorem, normal distribution, and Z-score. Each concept is explained in a simple, non-mathematical manner and illustrated with examples.
## Probability and its Significance
### What is the Probability?
Probability is a fundanmental concept in Data Science that quantifies the likelihood of an event or outcome. The probability of an event is always between 0 and 1. If the probability of an event is 0, it means that the event is impossible. On the other hand, if the probability of an event is 1, it means that the event is certain.

Life is inherently uncertain, with outcomes of various situations remaining unknown until they occur. Questions about weather, academic success, sports outcomes, and career advancements exemplify these uncertainties. These scenarios will be related to common terminologies used in our subsequent discussion:

- **Experiment**: refers to situations with uncertain outcomes, such as daily weather patterns.
- **Outcome**: is the result of a single instance of an experiment. For instance, if it is a sunny day, the outcome of today's weather experiment is "Sunny day"
- **Event**: is one or more outcome from an experiment. "Sunny day" is a possible event for the weather experiment.
- **Probability**: quantifies the likelihood of an event. If there’s a 80% chance of rain tomorrow, the probability of the outcome “Sunny day” for tomorrow’s weather experiment is 0.8.

### Significance
Probability allows Data Scientists to make sense of data and build reliable models. It is used in a wide variety of tasks, including data cleaning and preprocessing, exploratory data analysis, machine learning, and natural language processing. For example, a data scientist might use probability to develop a model to predict the likelihood of a customer defaulting on a loan, recommend products to customers based on their past purchase history, or predict the risk of a patient developing a certain disease. robability is a powerful tool that can be used to solve a wide range of problems in data science. By understanding probability, data scientists can make better decisions and build more reliable models.

## Random Variables
A random variable is a function that assigns a numerical value to each outcome of a random experiment. Random variables can be either discrete or continuous.
### Discrete Random Variable

A discrete random variable is a random variable that can only take on a finite number of distinct values, such as 0, 1, 2, 3, 4, and so on. The probability distribution of a discrete random variable is a list of the probabilities associated with each of its possible values. This list is known as the **propability mass function** (PMF). The PMF of a discrete random variable must satisfy two conditions:
- **Condition 1**: The probability of each value of the discrete random variable must be between $0$ and $1$.
- **Condition 2**: The sum of the probabilities of all the values of the discrete random variable must be 1.
For instance, suppose we are interested in the number of heads that will appear when a coin is tossed three times. The possible values of the random variable X are 0, 1, 2, and 3. The PMF of X is given by:

    ![Example sdfds](posts/2023-10-01-probability/table.png)

The table provides the following probabilities for a discrete random variable:
- There's a chance of getting $0$ ($P(X=0) = 0.1$).
- There's a chance of getting $0$ ($P(X=1) = 0.4$).
- There's a chance of getting $0$ ($P(X=2) = 0.3$).
- There's a chance of getting $0$ ($P(X=3) = 0.2$).
The sum of these probabilities gives us a total of 1 ($0.1 + 0.4 + 0.3 + 0.2 = 1$), which confirms that the sum of the probabilities for all possible values of the discrete random variable is indeed $1$, as it should be in any probability distribution.

Here is a simple example of a random discrete variable in Python:
```
    import numpy as np
    # Define the probability distribution
    p = np.array([0.1, 0.4, 0.3, 0.2])

    # Define the random variable
    X = np.random.choice([0, 1, 2, 3], p=p)

    print(X)
```
### Continuous Random Variable
A continuous random variable is a random variable that can take on any value in an interval. This means that there are infinitely many possible values for the variable. Continuous random variables are often used to represent quantities that can be measured infinitely precisely, such as height, weight, or temperature.

In detail, examples of continuous random variables include:
- The amount of rain in a city in a year
- The height of a randomly selected person
- The time it takes to complete a task
- The temperature on a given day

The probability distribution of a continuous random variable is known as the **probability density function** (PDF). Suppose $\displaystyle X$ is a continuous random variable with a probability distribution function $\displaystyle F_X(x)$. If the function $\displaystyle f_X(x)$ exists such that:
$$
  \displaystyle  F_X(x) = \int_{-\infin}^xf_X(t)dt
$$
then $\displaystyle f_X(x)$ is called the **probability density function** (PDF) of the random variable X.

The PDF of a continuous random variable must satisfy three conditions:
- $\displaystyle f_X(x) \geq 0,\ \forall x \in R$
- $\displaystyle P(a<X<b) = \int_a^bf_X(x)dx$
- $\displaystyle \int_{-\infin}^{\infin}f_X(x)dx = 1$

Here are some examples of probability density functions for continuous random variables:
- **Uniform distribution**: The probability of any value between a and b is the same. The PDF of a uniform distribution is given by $\displaystyle f(x) = \frac{1}{b-a}$
- **Normal distribution**: The normal distribution is a bell-shaped curve that is symmetric about the mean. The PDF of a normal distribution is given by $\displaystyle f(x) = \frac{1}{\sigma \sqrt{2\pi}} e^{-\frac{1}{2}(\frac{x-\mu}{\sigma})^2}$

<p style="text-align:center">
\(\theta_{t+1} = \theta_{t} - \dfrac{\eta}{\sqrt{\hat{v}_t} + \epsilon} \hat{m}_t\).
</p>