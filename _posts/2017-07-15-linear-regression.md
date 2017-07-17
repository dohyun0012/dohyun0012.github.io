---
layout:     post
title:      Linear Regression
date:       2017-07-15
categories: jekyll post
---
<script type="text/javascript" async
  src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.1/MathJax.js?config=TeX-MML-AM_CHTML">
</script>

Let's start from the most basic intuition. Take a look at this scatter plot of data. You may notice immediately that there is a certain linear relationship between variable x and variable y in a sense that increasing one variable seems to increase the other variable some fixed amount. How can we describe this relationship so that if someone gives us one variable, we can predict the other variable? One way is to take out a ruler and a pencil and draw a line through these data points that you think does a good job of representing the relationship. You may recall this exercise from middle school (elementary school?). However, is this really the best line? What does "best" really mean in this context?

You might be dismayed (or thrilled) to hear that there are more than one ways of defining the best fit line. The most intuitive way for me is to simply take a look at the residuals and find the line that minimizes the sum of these residuals. This is in fact one way of going about this, and it is called minimizing the absolute error, but the math behind actually finding the line that minimizes this sum is quite involved and is outside the scope of the blog. A seemingly more popular and mathematically cleaner way to find the best fit line is to take a look at the square of the residuals and find the intercept and slope that minimizes this sum. Take a look at the chart and notice a slight difference. Minimizing this sum of squared residuals is called ordinary least squares, and it considers outliers more seriously (the residual for the outlier is going to be large, and squaring that is even larger, so the algorithm will try to get as close to the outlier as possible).

Now, let's take a look at how we can actually find the parameters for the best fit line using ordinary least squares, i.e. the intercept and slope. Keep in mind that this is the most basic form of linear regression where we have only two variables, aka simple linear regression.

# Ordinary Least Square (using partial derivatives)

http://coccweb.cocc.edu/srule/MTH244/other/LRJ.PDF  
messy to do with multivariate regression... hence linear algebra

$$Cost\ Function = Squared\ Errors = Q = \sum_{i=1}^{n} (y_i-(\theta_0 + \theta_1 x_i))^2 = \sum_{i=1}^{n} \epsilon_i^2$$

$$\dfrac{\partial Q}{\partial\theta_0} = -2\sum_{i=1}^{n}(y_i - (\theta_0 + \theta_1 x_i)) = 0$$

$$\dfrac{\partial Q}{\partial\theta_1} = -2\sum_{i=1}^{n}x_i(y_i - (\theta_0 + \theta_1 x_i)) = 0$$

$$\theta_0 = \overline y - \theta_1 \overline x$$

$$\theta_1 = \dfrac{n\sum_{i=1}^{n}x_i y_i - \sum_{i=1}^{n}x_i\sum_{i=1}^{n}y_i}{n\sum_{i=1}^{n}x_i^2 - (\sum_{i=1}^{n}x_i)^2}$$

# Ordinary Least Square (using linear algebra)

https://isites.harvard.edu/fs/docs/icb.topic515975.files/OLSDerivation.pdf

$$B = (X^{T}X)^{-1}X^{T}Y$$

but apparently finding the inverse matrix has a complexity of O(n^3)... so we need a more efficient solution

# Ordinary Least Square (using gradient descent)

https://spin.atomicobject.com/2014/06/24/gradient-descent-linear-regression/

Use partial derivatives of the error function and the random initial parameters (slope and intercept) to get gradients.  
Update with gradient weighted by the learning rate*, use the new parameters (slope and intercept) to get new gradients.  
Repeat

* There are a few ways to find the right learning rate, but in any case, to check, the cost function should be going down with each iteration: http://blog.datumbox.com/tuning-the-learning-rate-in-gradient-descent/ (how does sciki-learn do it?)

partial derivatives:
$$\dfrac{\partial}{\partial \theta_1} = \dfrac{2}{N}\sum_{i=1}^{N}-x_i (y_i - (\theta_1 x_i + \theta_0))$$

$$\dfrac{\partial}{\partial \theta_0} = \dfrac{2}{N}\sum_{i=1}^{N}-(y_i - (\theta_1 x_i + \theta_0))$$

# Absolute Error

$$Cost\ Function = Squared\ Errors = Q = \sum_{i=1}^{n} |y_i-(\theta_0 + \theta_1 x_i)| = \sum_{i=1}^{n} \epsilon_i$$

not as easy to solve this optimization problem, i.e. find the minimum of this... https://en.wikipedia.org/wiki/Least_absolute_deviations

# Ridge

# Lasso

# How does sklearn actually implement all of this?
