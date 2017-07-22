---
layout:     post
title:      Music Discovery
date:       2016-09-24
summary:    Previously, music recommenders were just like your friends that shared good music with you. Now, we turn them into hipster music snobs chasing fresh new songs with data science.
categories: jekyll pixyll
---

For large scale recommendation systems, collaborative filtering has been the industry standard algorithm for quite some time. In music, this algorithm will recommend you songs that other people with similar tastes as you are enjoying. This works very well for music with existing usage data. However, this algorithm fails to recommend brand new songs or newer songs that only a few people have listened to. Also known as a cold start problem, this is a major weakness of the collaborative filtering algorithm. There are a lot of great new songs which people may want to check out, so how do we integrate these new songs into our recommendation engine?

One way to address this problem, as introduced by Aäron van den Oord, Sander Dieleman, and Benjamin Schrauwen in their [paper](https://papers.nips.cc/paper/5004-deep-content-based-music-recommendation.pdf) published at NIPS, is to use a convolutional neural network to listen to a clip of new songs to predict what the collaboritive filtering algorithm would have done. This model takes in as its input the actual audio content of the songs! In a sense, the model is "listening" to the songs. So what is this convolutional neural network trying to predict? It turns out that the collaborative filtering algorithm, more specifically weighted matrix factorization, will make a vector representation of each song. This vector has numbers called latent features which measures a certain "direction" of the sound in the space of music. For instance, the first number may tell you how "rock" the song is (recall that this is all based on user behavior, not the actual audio content nor any genre labels). This song vector is what the convolutional neural network is trying to predict by listening to the songs.

I trained a convolutional neural network and can now predict the vector representation of new songs and unpopular songs so that we can recommend them! To demonstrate that the model actually learned and is outputting something reasonable, I plotted the vector representation of 10,000 new songs that the model has not previously heard onto a 2-dimensional TSNE graph. You can check out my interactive TSNE map built with d3 [here](http://dohyunshin.com/etc/music-app/index.html). You can zoom in (scroll) to the clusters on the left side and will find that many of these clusters represent electronic songs. Here are some electronic songs you can input (just type in the song name in the query and hit enter):

* Mooore by RJD2
* Do Geese See God? by Mochipet
* Junktion by Peverelist
* Magicman by Bonobo
* Wabby Legs by AFX

The idea is that any new song will become a dot on this map, and we can recommend this new song to people who listen to songs close to this dot! You can also find the code to this project on my [Github page](https://github.com/dohyun0012/music-discovery).
