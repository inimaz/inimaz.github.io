---
title: "Guess your vote using Twitter"
excerpt: "Combining Twitter API and NLP"
header:
  teaser: /assets/images/twitter-vote/logo.jpg
gallery:
  - url: /assets/images/twitter-vote/sanchezcastejon.Cloud_of_words.png
    image_path: assets/images/twitter-vote/sanchezcastejon.Cloud_of_words.png
    alt: "placeholder image 1"
  - url: /assets/images/twitter-vote/sanchezcastejon.Cloud_of_Hashtags.png
    image_path: assets/images/twitter-vote/sanchezcastejon.Cloud_of_Hashtags.png
    alt: "placeholder image 2"
  - url: /assets/images/twitter-vote/sanchezcastejon.Cloud_of_User_mentions.png
    image_path: assets/images/twitter-vote/sanchezcastejon.Cloud_of_User_mentions.png
    alt: "placeholder image 3"
---
![alt text](../../assets/images/twitter-vote/logo.jpg)

**Initial note**:This proyect was done just before the Spanish elections of 10th November 2019.

**Goal**:
Can we guess the party that someone will vote just with their Twitter user?

We are importing data from Spanish twitter accounts and analizing them with some basic NLP. The goal is a very basic one: We get someone´s last 200 tweets (that´s the limit of the Twitter API) and we predict the party she/he might vote.

**Stack used**: Python, nltk (cleaning the data), sklearn (predictions) and Twitter API (to extract the tweets).

# TL;DR

We used random forest, logistic regression and k-neighbours to obtain the best prediction model.
Interestingly enough, the model was able to tell between right-wing and left-wing parties. The exception  


# Obtaining data

We need data to train our models. In other words, we need tweets from known voters of each party.
This was the full pipeline to obtain the data. We just needed as input per each user:
* Twitter UserId
* Party that it belongs to (the flag)

## Choosing flag users

We need Twitter users that are **openly voters** of each party. We selected the 6 parties that will have more votes in next elections (according to pools).

PP, Ciudadanos (CS), PSOE, UnidasPodemos (UP), VOX and MasPaís (MP).

From each party we obtained the tweets of:
* Official Twitter account of the party.
* Main polititian
* 5 other members of the party (taken from Senate/Parlament list). In case of MP we just googled 

## Data pipeline
The process that we followed was:
1. Get all tweets from the user (Twitter API has a limit on 200 tweets)
2. Store all Twitter info in 2 csv files (one with user info + another one with tweets info)
3. Clean tweets:

    1. Remove punctuation
    2. Save hashtag/user mentions/ emoticons into lists
    3. remove url, Spanish laugh,
    4. split tweet text into words
    5. stem the words (to keep only the root) and count vectorize them.
4. Create a word cloud with most used words/hashtags/mentioned users
5. Add this user to tweet DB (csv file)

At the end we have a file with all the users + another with all the tweets. Ah, and wordclouds to explain graphically a summary of the tweets of each user.

{% include gallery caption="Most-used words,most-used hashtags and most-mentioned users of the Spanish president, Pedro Sanchez." %}

# Choosing the best ML model
We train 4 different models to evaluate their performances: decission tree, random forest, logistic regression and k-neighbours.
In here we show the confusion matrix and the accuracy score of each model:

We choose to go ahead with the  model.

# Some insights taken from the confusion matrix

# Try to guess the vote of a twitter user


# Some dead ends

When starting a project like this there are many promising paths to follow. And 

## Sentiment analysis

This is hard to do in Spanish. Most sentiment analysis (SE) libraries are using corpus in English. Therefore, we have several options:

1. Translate our tweets to English to use SE from an already-built library like textblob or word2vec. This could work as a proof of concept, but not as a definitive version.
2. Create our own corpus. Lots of classification needed
3. Try to find a corpus in Spanish in the web. TASS was releasing until 2018 a corpus of Spanish tweets, but now it is hard to find it.


Blocking point for 1. Googletrans has a limit of 15k char per request. And might block the IP if you take too many requests... So it works up to some point... Any other way of translating?

## Locating tweets in map

Most of the users have their location turned off. This is wise for a public figure, but for this poject means we cannot locate their tweets.

# How to improve
* It takes long time to compute. Try to run it on GNU or on AWS/GCP server.
* Apply more cross validation and parameter tuning to each model. Due to the slow computing time, it was hard to optimize all the parameters.
* Try to do it with Neural Networks.

# Some related links
* Inspired by [https://rodolfoferro.xyz/sentiment-analysis-on-trumps-tweets/](https://rodolfoferro.xyz/sentiment-analysis-on-trumps-tweets/)
* [NLP intro (in Spanish)](https://likegeeks.com/es/tutorial-de-nlp-con-python-nltk/)
* [Twitter API](https://developer.twitter.com/en/docs)
