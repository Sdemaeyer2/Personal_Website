---
abstract: Recently I held a talk on Bayesian anlaysis and how to simply run them in R, making use of the `brms` package. Hereby attached the pdf (in Dutch). 
all_day: false
authors: []
date: "2019-05-14T10:00:00Z"
date_end: "2019-05-14T12:00:00Z"
event: EduBROn Lunch Seminar
event_url: 
featured: true
image:
  caption: ""
  focal_point: Right
links:
location: Antwerp, Belgium
math: true
projects:
publishDate: "2019-06-09T00:00:00Z"
slides: 
summary: A pdf of a presentation on Bayesian analyses in R.
tags: [Bayesian]
title: Introduction to Bayesian analysis with R
url_code: ""
url_pdf: ""
url_slides: ""
url_video: ""
---

{{% alert note %}}
You can download the pdf here: [Bayesian_intro_Sven.pdf](Bayesian_intro_Sven.pdf).
{{% /alert %}}

The majority of research relies on statistical analyses that are in general grounded within Null-Hypothesis Significance Testing (NHST). But NHST has it's 'downsides'. First of all, NHST tests a 'null-hypothesis' rather than the real research hypothesis we're interested in. And secondly, NHST makes use of *imaginary* samples (the sampling distribution). Finally, NHST doesn't quantify the uncertianty of parameters. 

The framework of Bayesian analysis is a tool that can overcome these flaws of NHST. In this talk I introduced the basic idea of Bayesian analysis, the way Markov Chain Monte Carlo works (conceptually) and how to implement it in R making use of the `brms` package to compile code for Stan (an mcmc sampler in C++). The talk is a gentle introduction (in Dutch). 