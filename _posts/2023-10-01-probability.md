---
layout: post
read_time: true
show_date: true
title: "Fundanmentals of Probability illustrated with Python examples"
date: 2023-09-28
img: posts/2023-10-01-probability/thumbnail.webp
tags: [probability, ai, data science]
category: theory
author: Gia-Huy Vuong
description: "This guide provides an introduction to Probability, a crucial concept in Data Science. To begin with, we will discuss about the basic topics of Probability, such as binomial distribution, central limit theorem, normal distribution, and Z-score. Each concept is explained in a simple, non-mathematical manner and illustrated with examples."
toc: yes
---
## Overview
This guide provides an introduction to Probability, a crucial concept in Data Science. To begin with, we will discuss about the basic topics of Probability, such as common distributions, central limit theorem, and Z-score. Each concept is explained in a simple, non-mathematical manner and illustrated with examples.
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

    ![Example](assets/img/posts/2023-10-01-probability/table.png)

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

<p style="text-align: center;">$\displaystyle F_X(x) = \int_{-\infty}^xf_X(t)dt$
</p>

then $\displaystyle f_X(x)$ is called the **probability density function** (PDF) of the random variable X.

The PDF of a continuous random variable must satisfy three conditions:
- $\displaystyle f_X(x) \geq 0,\ \forall x \in R$
- $\displaystyle P(a<X<b) = \int_a^bf_X(x)dx$
- $\displaystyle \int_{-\infty}^{\infty}f_X(x)dx = 1$

<!-- Here are some examples of probability density functions for continuous random variables:
- **Uniform distribution**: The probability of any value between a and b is the same. The PDF of a uniform distribution is given by $\displaystyle f(x) = \frac{1}{b-a}$
- **Normal distribution**: The normal distribution is a bell-shaped curve that is symmetric about the mean. The PDF of a normal distribution is given by $\displaystyle f(x) = \frac{1}{\sigma \sqrt{2\pi}} e^{-\frac{1}{2}(\frac{x-\mu}{\sigma})^2}$
- **Exponential distribution**: The exponential distribution is used to model the time between events that occur continuously and independently at a constant average rate. The PDF of an exponential distribution is given by $\displaystyle f(x) = \lambda e^{-\lambda x}$ -->

To generate a random number from [the uniform distribution](#uniform-distribution) in Python, we can use the ``numpy.random.uniform()`` function. This function takes two arguments: the minimum and maximum values of the distribution. For example, the following code generates a random number from the uniform distribution between 0 and 1:
```
import numpy as np

# Generate a random number from the uniform distribution between 0 and 1
random_number = np.random.uniform(0, 1)

# Print the random number
print(random_number)
```
## Common distributions
### Binomial distribution 
The binomial distribution is a discrete probability distribution that describes the likelihood of a specific number of successes in a sequence of n independent trials, each with two possible outcomes (success or failure). The binomial distribution serves as a fundamental cornerstone in social science statistics, particularly when modeling outcomes with two possible results. For example, it can predict a Republican or Democrat will win an upcoming election, whetheran individual will die within a specified period of time, etc. It also has applications in finance, banking, and insurance, among other industries. 

To illustrate my point, let’s consider a funny example involving a dog named Lucky:

Lucky is a very curious cat and has a peculiar habit. Every time he sees a red laser pointer, he tries to catch it. Let's say that the probability of his successfully catching the laser point on any given attempt is 20%. 

Now, suppose his onwer decides to play with him using the laser pointer and gives Lucky 10 attemps to catch it. We want to find out the probability that Lucky will successfully catch the laser pointer exactly 3 times out of these 10 attemps.

This is a classic example of a binomial distribution problem. In a binomial distribution, there are two possible outcomes for each trial, and the probability of success on each trial is the same. In this case, the two possible outcomes are "catch" and "miss", and the probability of catching the laser pointer on each attempt is 0.2.

To calculate the probability that Lucky will catch the laser pointer exactly 3 times in 10 attempts, we use the binomial distribution formula:

<p style="text-align: center;">$\displaystyle P(X=k) = {n \choose k}p^k(1-p)^{n-k}$
</p>
where:

- n is the number of trials (10 in this case)
- k is the number of successes (3 in this case)
- p is the probability of success on each trial (0.2 in this case)

Plugging in these values, we get:
<p style = "text-align: center;">
P(X = 3) = $\displaystyle {10 \choose 3}*0.2^3*(1-0.2)^{10-3} = 0.193$
</p>

In addition, you can use the ``scipy`` library in Python, which has a built-in function to calculate binomial distribution. Here’s how you can do it:

```
from scipy.stats import binom

# number of trials
n = 10

# probability of success
p = 0.2

# number of successes
k = 3

# calculate binomial distribution
prob = binom.pmf(k, n, p)

print(f"The probability that Lucky will catch the laser pointer exactly {k} times in {n} attempts is {prob}")
```

### Normal distribution
The normal distribution, also known as the Gaussian distribution, is a continuous probability distribution that is symmetric and bell-shaped. It is the most commonly used distribution in data science, and it is often used to model continuous data such as height, weight, and test scores. The general form of its probability density function is:

### Exponential distribution
The exponential distribution is a continuous probability distribution that describes the time it takes for a single event to occur. It is often used to model event data such as the time it takes for a customer to arrive at a store or the time it takes for a radioactive atom to decay.
<!-- - **Exponential distribution**: The exponential distribution is used to model the time between events that occur continuously and independently at a constant average rate. The PDF of an exponential distribution is given by $\displaystyle f(x) = \lambda e^{-\lambda x}$ -->
### Uniform distribution
The uniform distribution is a continuous probability distribution in which all values between a minimum and maximum value are equally likely. It is often used to model random data such as the time of day that a customer arrives at a store or the location of a click on a website.
### Poisson distribution
The Poisson distribution is a discrete probability distribution that describes the likelihood of a certain number of events occurring in a fixed interval of time or space. It is often used to model count data such as the number of customers arriving at a store in an hour or the number of goals scored in a soccer match.