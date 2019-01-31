---
layout:     post
title:      Hypothesis Testing
date:       2019-01-19
categories: jekyll post
---
<script type="text/javascript" async
  src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.1/MathJax.js?config=TeX-MML-AM_CHTML">
</script>

A business decision maker should know, based on intuition and business sense, what decisions to make in absence of data (default actions). These default actions are supported by the null hypothese (e.g. there is no difference between the two versions, so we'll go ahead and apply the new version as it looks nicer). The role of hypothesis testing is to be able to tell when there is significant evidence to support NOT taking default action and rather take the alternative action, which is supported by an alternative hypothesis. 

Here is how the hypothesis test is run:

Use proof by contradiction. Assume that your null hypothesis is true. If there is contradiction, then you can assume that the alternative hypothesis is true.

Example:

Assume null hypothesis is true and that there is no difference in the summary test statistic (ex. mean, proportions, chi-squared) between the two groups. In that case, we can think of the difference as a parameter with a sampling distribution centered around 0 with a normal distribution thanks to the Central Limit Theorem. Furthermore, we can estimate the standard error of this sampling distribution by pooling the standard deviation of the two samples. Lastly, we can even standardize this parameter by dividing it by the standard error, turning it into z-score. (somewhere in here, we need to use n-1 to handle bias from sampling).

Now that we have this sampling distribution for the test statistic, we can see where the observed test statistic lands on this sampling distribution. The chance of observing what we observed or something more extreme is called the p-value. If p-value is below the alpha level, then we say that there is contradiction or that there is enough evidence to reject the null hypothesis. Given a test statistic, +/-2 standard error from the test statistic gives us a 95% confidence interval, and there is 95% chance that the real parameter lies somewhere on this interval.

The above analysis can be done analytically, but we can also use simulations:
* compare method of pooling standard deviation and looking at the two sampling distributions separately.

Assume null hypothesis is true, then we should be able to combine the data from our two groups, shuffle, create two new groups, calculate the means, repeat multiple times, and see a distribution that represents, supposedly, both of the groups. Look at the actual difference between the means. If less than 5% of the distribution had a difference as big as or bigger than the actual difference, then we say that there is contradiction. Statistically speaking, there is strong evidence that the null hypothesis is false.

The absolute difference between the means is one example of a test statistics, but other examples include non-absolute difference between the means (one-sided hypothesis testing), standard deviation, correlation, and proportions. All of these test statistics can be tested by assuming null hypothesis and running **SIMULATIONS!!** (Role of CTL?)

Test statistic for proportions may be absolute deviation. For instance, with a die roll, we can sum the absolute deviation from expected and actual. However, a chi-squared, which squares the deviation, might be better since it puts more weight on large deviation in a single possibility, like a six being rolled particularly a lot.

Statistical significance does not tell you anything about the actual effect size. Also, it's possible for two groups to be exactly the same, in which case more sample sizes will make them converge to the same mean, and p-value may never dip. (I should test this with simulations)

Significance level is the false positive rate (calling it significant when it isn't). False negative rate is determined by power (calling it not significant when it actually is). Significance level can be set for the experiment. Power is more complicated because it depends on the actual effect size. One option is to assume the observed effect size is accurate and simulate. Failing power ("underpowered") suggests that if there is an actual difference like the observed effect size or some hypothetical baseline effect size, it is too small to detect with the current sample size.

Running multiple tests on the same dataset or exploring/finding effect and running a test will increase false positive rate. You can lower the significance level or split the dataset into exploration set and a testing set.


Conditions that have to be met for Z-test is
1) Random condition - sample is drawn randomly and there is no bias (i.e. the average of the estimates will converge to mean)
2) Normal condition - the count of success and failure are both at least 10, then normal approximation holds
3) Independence condition - sample size is less than 10% of the population, or else drawing from the population without replacement can change makeshift of the population


Reference: "Practical Statistics for Data Scientists" book
