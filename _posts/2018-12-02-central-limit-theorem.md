---
layout:     post
title:      What Is Correlation?
date:       2018-12-01
categories: jekyll post
---
<script type="text/javascript" async
  src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.1/MathJax.js?config=TeX-MML-AM_CHTML">
</script>

Covariance = How two variables deviate from their respective means in tandem
           = Dot product (measuring similarity) of the variable's deviations from the mean
           = dot(de_mean(x), de_mean(y)) / (n-1)
Correlation = Standardizing the unit of covariance
            = Covariance / stdev_x / stdev_y

Correlation, just like the mean, is sensitive to outliers


Correlation explained:

Consider we want to look at the correlation between height and weight. We first want to turn the values in these two variables into some comparable units or standard units: (x_i - x_mean) / std dev. (can be positive or negative around the mean)

Afterwards, we want to multiple these standard units such that for each observation, we can a large positive number if the variables are both deviating in the same direction from the mean, large negative number if deviating in opposite direction.

We then sum these products and divide by number of observations. If the deviations are all in same direction or all in opposite direction, correlation will have a large positive or negative number (close to -1 or 1). If not, positive will cancel out negative, and correlation will be 0.
