---
title: 5 terms of Bayesian Stats you should understand
author: Sven De Maeyer
date: '2019-07-03'
slug: how-to-understand-bayesian-analyses
categories:
  - R
  - Bayesian
  - Statistics
tags:
  - Bayesian
subtitle: ''
summary: ''
authors: []
lastmod: '2019-07-03T22:29:21+02:00'
featured: no
image:
  caption: ''
  focal_point: ''
  preview_only: no
projects: []
---


```r
library(tidyverse)
```

```
## ── Attaching packages ─────────────────────────────────────────────────────────────────────────────── tidyverse 1.2.1 ──
```

```
## ✔ ggplot2 3.2.0     ✔ purrr   0.3.2
## ✔ tibble  2.1.3     ✔ dplyr   0.8.3
## ✔ tidyr   0.8.3     ✔ stringr 1.4.0
## ✔ readr   1.3.1     ✔ forcats 0.4.0
```

```
## Warning: package 'ggplot2' was built under R version 3.5.2
```

```
## Warning: package 'tibble' was built under R version 3.5.2
```

```
## Warning: package 'tidyr' was built under R version 3.5.2
```

```
## Warning: package 'purrr' was built under R version 3.5.2
```

```
## Warning: package 'dplyr' was built under R version 3.5.2
```

```
## Warning: package 'stringr' was built under R version 3.5.2
```

```
## Warning: package 'forcats' was built under R version 3.5.2
```

```
## ── Conflicts ────────────────────────────────────────────────────────────────────────────────── tidyverse_conflicts() ──
## ✖ dplyr::filter() masks stats::filter()
## ✖ dplyr::lag()    masks stats::lag()
```

More and more in research we get confronted with colleagues that apply Bayesian analyses. They use a specific vocabulary: "posterior distribution", "Highest Probability Density Intervals", "priors", "MCMC", "burn-in", ... But what's the meaning of these terms? And how to interpret the essentials of Bayesian analyses? 

In this post I'll try to explain the basics and explain 5 key concepts. But before that, a short notice on the goal of stats (because sometimes we seem to forget).

# Stats? Why?

To put it simple: stats help us to model reality in numbers. Let's say we have a major concern on the rise of *vampires* in Europe ^[Ok. We can have serious doubts about whether this is the best example to demonstrate how we *model reality*]. The major question then is: how many vampires are out there? This is a statistical question that can be approached by a pretty simple *model*: a percentage of Vampires among the whole population of Europeans. This model only contains one unknown value - the actual percentage of Vampires - This unknown value is what we often call *a parameter*. In the exceptional case that we can test anyone of the whole European population we can calculate the exact percentage. But that's utopia. In research most of the time we make use of samples (we test a random choosen number of European citizens) and we do not calculate the exact parameter value. We *estimate* the parameter value. Actually statistics help us to estimate parameter values. But it does even more. Good statistics also *quantifies the (un)certainty* on our parameter estimates! If we apply this to our question concerning the percentage of Vampires in Europe, we want statistics to help us quantify how certain we are about different percentages of vampires as the true number in the population.

This brings us to our two first concepts from Bayesian analysis: priors and posteriors.

# Priors and posteriors

Bayesian statistics calls the quantification of uncertainty on parameter estimates <u>**priors and posteriors**</u>. So both concepts refer to some kind of probability. 

Lets start with the prior. 

> A prior is a quantification of (un)certainty on parameter estimates that we have before we consider the information in the data that we gather. 

If we apply this to our example of vampires, a prior quantifies our prior knowledge on the probability of each possible percentage of vampires in Europe. In this case this means that we, as researchers, allocate a probability to each possible percentage of vampires that this percentage is the true percentage in the European population. Now, imagine in this case that we do not have any clue before we start a research than each percentage has the same probability. The next plot shows our prior! Note that we have no data yet. So this graph visualizes our prior knowledge about the proportion of vampires.

<img src="/post/2019-07-03-how-to-understand-bayesian-analyses_files/figure-html/unnamed-chunk-2-1.png" width="672" />

Of course, in research we gather **data**. In our example we're lucky that prof. dr. Van Helsing ^[Prof.dr. Van Helsing first appeared in the novel "Dracula". He's the vampire hunter.]. He developed the ultimate *Vampire Test* that determines whether a person is a vampire or not. With some sponsoring of the European Commission he was able to draw a random sample of 200 Europeans and applied his test. 

<img src="/post/2019-07-03-how-to-understand-bayesian-analyses_files/figure-html/unnamed-chunk-3-1.png" width="672" />



```r
prop_model(Vamp_data_weinig)
```

<img src="/post/2019-07-03-how-to-understand-bayesian-analyses_files/figure-html/unnamed-chunk-4-1.png" width="672" />

