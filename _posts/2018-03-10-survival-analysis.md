---
layout:     post
title:      Survival Analysis Demystified
date:       2018-03-10
categories: jekyll post
---
<script type="text/javascript" async
  src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.1/MathJax.js?config=TeX-MML-AM_CHTML">
</script>

Born out of the medical field, survival analysis is used to answer questions like "what is the lifetime of a patient with kidney cancer", "at a given point in time, what is the risk of death (hazard rate) for a patient that has had kidney cancer for six months?".

In addition to being answer these questions, methods were developed to utilize information other than time, for example, a patient's age, gender, weight, etc. Termed survival regression, this technique was used for predictive modeling.

More recently, survival analysis and survival regression has become relevant in the field of data science as it applies to predicting churn. For example, a SaaS company would want to know users that are at the highest risk of churn.

One method of predicting churn is use typical machine learning models on a dataset where each row is a user, and the fields contain time since joining, other predictive variables, and whether they have churned or not. Here is the issue with this approach. Our Y variable here is whether they have churned of not, but while the user has not churned YET, they could in the future. It is difficult to frame this problem as a simple binary classification problem. Survival analysis deals with this by acknowledging that no churn does not mean 0 but rather that the user has not yet churned. This is formally called right censoring.

The survival analysis method of predicting churn is to take right censoring into account to predict the hazard rate for the user at the given time, considering all the other variables as well. These models require covariates and two special columns, one for the duration and the other for whether the event occurred (churn in this case).
