---
layout:     post
title:      Bayes Theorem
date:       2018-04-22
categories: jekyll post
---
<script type="text/javascript" async
  src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.1/MathJax.js?config=TeX-MML-AM_CHTML">
</script>

If independent:

P(E,F) = P(E)P(F)   (1)

Condition probability:

P(E|F) = P(E,F)/P(F)   (2)

hence P(E,F) = P(E|F)P(F)   (3)

So when independent, P(E|F) = P(E)   (4)

Bayes Theorem, apply conditional probability twice (keep in mind P(E,F) = P(F,E)):

P(E|F) = P(E,F)/P(F) = P(F|E)P(E)/P(F)   (5)

also, P(F) = P(F,E) + P(F, not E)   (6) --> mutually exclusive events

so P(E|F) = P(E,F)/P(F) = P(F|E)P(E)/(substitute P(F) with formula above and replace components with formula from (3))
