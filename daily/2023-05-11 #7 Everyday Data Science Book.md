---
date : "2023-05-11"
title : "#7 Everyday Data Science Book"
slug : "7-everyday"
time : "5h-35m"
summary : "I finished reading a book, here’s the review and notes"
---

## Progress

Today, I finished reading the book "Everyday Data Science" by Andrew Carr. I had it downloaded a long time ago, when searching for introductory books on data science.

---

## Review

I did engineering and have past experience programming. I try keeping away any bias that I might've creeped in, but I can't ever be so sure. My context should help you form a better picture.

Before getting into the actual content. This is a very short book, 94 pages only and if you consider the fact each chapter ends with a blank page. As Most of the text uses only left half of page, one could really trim it down to a blog post, a long one but a blog post for sure, albeit 2 parts.

But that doesn't make it a bad book. I guess, it's supposed to be that way. A quick one read book to finish on a Saturday afternoon. For someone who has seen all fuzz about going on around data science, and wishes to know more.

The author, Andrew, starts with explaining what is and isn't data science in the first chapter. Next seven chapters are all but examples (mostly real world) where someone is facing an issue. Data Science comes as a hero with a new 'concept' and saves the day. Everyone lives happily ever after. I wish there was a rainbow at then of the book, I wished and hoped they'll be one.

But in all seriousness, this is a good book to get a taste of what data science could look like without putting any effort in actually learning it.

4/5 Stars.

---

## Book Notes

### Data Science 101

Life is full of decisions. Everyday decisions can have significant direct and indirect effects. Decisions making can be improved by data.

Human memory has helped us for millions of years, but what's better than human memory ? Computer memory. Portable, Reliable, Duplicate-able, Cheaper, Replaceable, Delete-able. Image a computer getting embarrassed at something some it did five years ago. Nope, that isn't happening anytime soon. Guess what computers are also really good at ? Computing, duh! Only recently, we've started using computers to store and process huge amounts of data, to improve our decisions making.

That brings us to the question, what is data science then ? At it's core, data science is using data to make informed decisions.

A few more terms that can be found hang around in close proximity with 'data science' .

- Model : Using math/stat to explain/predict stuff
- Fit : Showing data to model, to make it better
- Graph : You already know what a graph is!
- discrete : ??

### Tests & Distributions

A/B Testing as the name suggest is way to test which is better, A? or B? Now, replace the the primordial alphabets with anything from the real world and put in a few fancy equations, we've just unlocked a fundamental statics model.

There are a lot more of these tests, one of the popular ones is 'pTest', which can be used to understand if the results were just random or they actually mean something.

In order to generate results we can use something called as "one armed bandit" (think of slot machines) that produces a random output. Each pull of lever will produce new output, i.e., more pulls(tries) more data. Though more data can be a nice thing, sometimes. Ideally, we would want to find the results with utmost certainty using fewest experiments(tries).

If there are only two possible outcomes (flipping of a coin) it's called 'Bernoulli distribution'. Another similar one is, Beat distribution, which has pairs of variables alpha (heads i.e., success) and beta (tails i.e., failure). If we record the number times we get heads and tails it, after a few tries we find that it'll reach an equilibrium, or a distribution. As the number of possible outcomes increases, we'll need more tries (events i.e., flips) to reach a uniform distribution. Distribution, here means that the possibility of each outcome. Thompson sampling is an algorithm that can be used to to tweak 'randomness' based on previous result, allowing us to reach equilibrium with fewer tries.

### Three Musketeers

Mean. Median. Mode.

Outliners i.e., extremities of data that can have huge impact on Mean. Unlike, Median. For mode, it depends.

Geometric Mean can be used compare items that are on different scales.

### Boxplots

It is a standardized way to show distribution of discrete data points. It can be drawn following these steps

- Draw a straight line (this represent median)
- Draw a box around it with previous line at center
- Q1 is the median of `median` and minimum value
- Similarly Q2 is median of `median` and maximum value

This results in making `median` or Q2 actually the median of `Q1` and `Q2`.

![[Import Image]]
??Search More

### ODE

Ordinary differential equations are used to relate how something changes with itself. They are useful when we don't have data. We can used ODE to describe a process and use results to make informed decisions what might happen in future.

One of the ODE model is `predator-prey model` that how populations of interacting predators and preys grows and shrinks over time.

### Time Series

Time series is a collection of data points, ordered in time. A time series can be better understood by features such as Stationarity, Seasonality & Autocorrelation.

In a `stationary` time series, mean and median don't change over time. `Seasonality` or periodicity as a name suggests has repeating functionality over a time. Think of sine wave. `Autocorrelaton` is correlation or connection of time series with some delayed copy of itself. In a function of time, how similar/far they are.

### Models

Moving average (MA) where the next prediction is the mean of previous observations. It has hyperparameter, q, referred to as order of model. Another model is, Auto Regressive (AR) in which prediction is linear combination of it's own previous values.

### Words & Vectors

> *a word is characterized by the company it keeps ~ Firth
The distance between tow words is a function of neighbors. ~ andrew*
> 

The distance between two things can be represented as `d(a,b)` where d is distance or a metric. Vector is list of numbers. The length of vector is its dimension.

We can have any words or sentences represented as vectors and then we can run calculations to find things like similarity between two sentences or predicting the next word.

This is the same principle that makes LLM work and the one that is powering ChatGPT.
