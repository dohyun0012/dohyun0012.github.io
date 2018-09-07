---
layout:     post
title:      A/B Testing
date:       2018-03-10
categories: jekyll post
---
<script type="text/javascript" async
  src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.1/MathJax.js?config=TeX-MML-AM_CHTML">
</script>

For example, suppose the task is to test whether a coin is fair (i.e. has equal probabilities of producing a head or a tail). If the coin is flipped 100 times and the results are recorded, the raw data can be represented as a sequence of 100 heads and tails. If there is interest in the marginal probability of obtaining a head, only the number T out of the 100 flips that produced a head needs to be recorded. But T can also be used as a test statistic in one of two ways:

the exact sampling distribution of T under the null hypothesis is the binomial distribution with parameters 0.5 and 100.
the value of T can be compared with its expected value under the null hypothesis of 50, and since the sample size is large a normal distribution can be used as an approximation to the sampling distribution either for T or for the revised test statistic T−50.
Using one of these sampling distributions, it is possible to compute either a one-tailed or two-tailed p-value for the null hypothesis that the coin is fair. Note that the test statistic in this case reduces a set of 100 numbers to a single numerical summary that can be used for testing.

Normal approximation to Binomial distribution is allowed by the Central Limit Theorem; i.e. average of Bernoulli trials is normally distributed.
