---
title: "Feature Store"
layout: post
categories: "Machine Learning"
tags: architecture, machine_learning, ai
published: false
toc: true
---

### Definition

* The process of creating features is called feature engineering. 


### Capabilities

Feature store is more complex, can be broken down into:
  * Identify feature that matters:
    * More of an art vs. science; long process of trial and error
    * Some are more systematic/ structured, e.g. BGI - Sensible, Predictive, Consistent and Additive
  * Pipeline to calculate and store it as part of operational pipeline
  * Online vs. offline features
    * Not just about mechanics/process, but think of it from feature characteristics standpoint:
      * Offline - calculation part of batch job, creating these can take time (volume/ size of data, etc.) Also, these are "slow", i.e. features are "stationary" (terminology used loosely)
      * Online - calculation needed fast, served in millisecond latency. E.g. z-score for real-time fraud detection. Sliding window, in-memory/ fast key-value database comes in handy
  * Discoverability/ catalog/ single pane of glass for sharing all available features
  * Data transformation service enabling users to manipulate raw data and store it as features ready-to-use by any machine learning model

### Benefits
* Faster development
  * Abstract data engineering layers, provide easy access for read and write
* Abstraction from difference in characteristics between offline and online, API to retrieve data
* Smooth model deployment in production
  * Features used in production (real-time, live) is different from those used in training. Lack of consistent feature set.
  * Prevent data skew
* Feature store can keep additional metadata, e.g. feature impact on the model it is associated with. Helps with future development, choose those that achieve better impact on similar existing models
* Better collaboration
* Track lineage (address regulatory compliance, better measurement, etc.)
* Feature store and MLOps
  * Quality of model based on both quality of code and data (unlike DevOps)
  * Automated feature engineering, trigger mechanism upon code changes (Git push) or arrival of new data




### Credit
* https://towardsdatascience.com/what-are-feature-stores-and-why-are-they-critical-for-scaling-data-science-3f9156f7ab4
