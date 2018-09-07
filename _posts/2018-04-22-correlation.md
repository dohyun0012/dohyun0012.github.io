---
layout:     post
title:      What Is Correlation?
date:       2018-04-22
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
