---
layout:     post
title:      Linear Regression
date:       2017-07-15
summary:    Demystefying linear regression
categories: jekyll pixyll
---

Some latex placeholders:

$$Cost\ Function = Squared\ Errors = Q = \sum_{i=1}^{n} (y_i-(\theta_0 + \theta_1 x_i))^2 = \sum_{i=1}^{n} \epsilon_i^2$$
$$\dfrac{\partial Q}{\partial\theta_0} = -2\sum_{i=1}^{n}(y_i - (\theta_0 + \theta_1 x_i)) = 0$$
$$\dfrac{\partial Q}{\partial\theta_1} = -2\sum_{i=1}^{n}x_i(y_i - (\theta_0 + \theta_1 x_i)) = 0$$
$$\theta_0 = \overline y - \theta_1 \overline x$$
$$\theta_1 = \dfrac{n\sum_{i=1}^{n}x_i y_i - \sum_{i=1}^{n}x_i\sum_{i=1}^{n}y_i}{n\sum_{i=1}^{n}x_i^2 - (\sum_{i=1}^{n}x_i)^2}$$
