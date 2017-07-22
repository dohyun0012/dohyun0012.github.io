---
layout:     post
title:      Humor Detection
date:       2016-09-07
summary:    Understanding humor is the first step to being funny. So can machines detect humor in text?
categories: jekyll pixyll
---

Humor is an interesting problem in artificial intelligence. If I can hold a long conversation with a computer and laugh at its humor, then I would be convinced that we are living in an AI age. The first step to creating a humorous AI agent would be to detect humor in text and have the machine understand what makes its funny.

The Yelp Dataset Challenge dataset contains more than two million Yelp reviews. Users can tag reviews as "Useful", "Funny", or "Cool". I gathered reviews which had more than 10 "Funny" tags to train my model.

There are layers of complexity involving context and predetermined notions when identifying humor in text. One would assume that "layers of complexity" makes this problem an appropriate setting for neural networks. The idea is that it will learn the subtleties and complex relationships between each word in a document of text. This post is an exploration of this idea inspired by a [paper](https://cs224d.stanford.edu/reports/OliveiraLuke.pdf) written by Luke de Oliveira and Alfredo Láinez Rodrigo from Stanford ICME.

Using standard NLP methods as well as word2vec, I turned texts into features and tried out several models. Logistic Regression and Naive Bayes were very successful, but my implementation of a simple neural network using TensorFlow did not work as well. It is likely the case that a more robust neural network like a convolutional neural network (CNN) or a recurrent neural network (RNN) will perform better.

Using my Logistic Regression model, I wrote a function that tells you whether what you say is funny or not. Unfortunately, the result right now is quite biased towards the actual words used in the reviews:

``` python
# Tells you whether what you said is funny or not
def funny_or_not(string):
    if log_pipe.predict(pd.Series([string])) == np.array([1]):
        print("You funny")
    else:
        print("You not funny")

funny_or_not("yolo swag 420")   # Made up text   
# Output: You not funny
funny_or_not("I am funny.")   # Made up text
# Output: You not funny
funny_or_not("Their bathroom was about as clean as a homicide.")   # Actual funny Yelp review
# Output: You funny
```

You can find the code for this project on my [GitHub page](https://github.com/dohyun0012/humor-detection).
