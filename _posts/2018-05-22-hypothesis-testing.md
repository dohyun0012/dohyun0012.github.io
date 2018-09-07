---
layout:     post
title:      Hypothesis Testing
date:       2018-05-22
categories: jekyll post
---
<script type="text/javascript" async
  src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.1/MathJax.js?config=TeX-MML-AM_CHTML">
</script>

You have a dataset. You have a hypothesis. You use proof by contradiction. Assume that your hypothesis is false. If there is contradiction, then you can assume it is true.

Your hypothesis being false means that the null hypothesis is true; e.g. there is no difference between the means. Well, assume that your the null hypothesis is true; i.e. there is no difference between the means. Then, we should be able to combine the data from our two groups, shuffle, create two new groups, calculate the means, repeat multiple times, and see a distribution that represents, supposedly, both of the groups. Look at the actual difference between the means. If less than 5% of the distribution had a difference as big as or bigger than the actual difference, then we say that there is contradiction. Statistically speaking, there is strong evidence that the null hypothesis is false.

The absolute difference between the means is one example of a test statistics, but other examples include non-absolute difference between the means (one-sided hypothesis testing), standard deviation, correlation, and proportions. All of these test statistics can be tested by assuming null hypothesis and running **SIMULATIONS!!** (Role of CTL?)

Test statistic for proportions may be absolute deviation. For instance, with a die roll, we can sum the absolute deviation from expected and actual. However, a chi-squared, which squares the deviation, might be better since it puts more weight on large deviation in a single possibility, like a six being rolled particularly a lot.

Statistical significance does not tell you anything about the actual effect size. Also, it's possible for two groups to be exactly the same, in which case more sample sizes will make them converge to the same mean, and p-value may never dip. (I should test this with simulations)

Significance level is the false positive rate (calling it significant when it isn't). False negative rate is determined by power (calling it not significant when it actually is). Significance level can be set for the experiment. Power is more complicated because it depends on the actual effect size. One option is to assume the observed effect size is accurate and simulate. Failing power ("underpowered") suggests that if there is an actual difference like the observed effect size or some hypothetical baseline effect size, it is too small to detect with the current sample size.

Running multiple tests on the same dataset or exploring/finding effect and running a test will increase false positive rate. You can lower the significance level or split the dataset into exploration set and a testing set.


Conditions that have to be met for Z-test is
1) Random condition - sample is drawn randomly and there is no bias (i.e. the average of the estimates will converge to mean)
2) Normal condition - the count of success and failure are both at least 10, then normal approximation holds
3) Independence condition - sample size is less than 10% of the population, or else drawing from the population without replacement can change makeshift of the population
