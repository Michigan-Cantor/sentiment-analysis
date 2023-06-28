## Cantor Twitter Sentiment Analysis Project

Cantor coding project 1 (adapted from Siraj Raval on Youtube)

### Project Overview

The goal of this project is to perform sentiment analysis on tweets related to a specific topic using the Twitter API, Tweepy library, and the TextBlob library in Python. The project aims to teach intermediate coders how to use machine learning techniques for sentiment analysis and enhance their understanding of Python programming. The completed code will be concise, consisting of approximately 40-50 lines, and will only use the Tweepy and TextBlob libraries.

### Prerequisites

Before starting the project, ensure that the following dependencies are installed:

Python (version 3.x)
Tweepy library (install using pip: pip install tweepy)
TextBlob library (install using pip: pip install textblob)

### Setup

a. Obtain Twitter API credentials:

Visit the Twitter Developer Platform (https://developer.twitter.com/en/apps) and create a new app.
Obtain the consumer key, consumer secret, access token, and access token secret.


b. Import the required libraries:

```
import tweepy
from textblob import TextBlob
```

c. Authenticate with the Twitter API:

```
consumer_key = 'CONSUMER_KEY_HERE'
consumer_secret = 'CONSUMER_SECRET_HERE'
access_token = 'ACCESS_TOKEN_HERE'
access_token_secret = 'ACCESS_TOKEN_SECRET_HERE'
```
```
auth = tweepy.OAuthHandler(consumer_key, consumer_secret)
auth.set_access_token(access_token, access_token_secret)
api = tweepy.API(auth)
```

### Retrieving Tweets

To retrieve tweets related to a specific topic, the code needs to perform the following steps:

```
public_tweets = api.search('Biden')
for tweet in public_tweets:
    print(tweet.text)
```
    
### Sentiment Analysis:

a. Performing sentiment analysis on tweets:
To analyze the sentiment of each tweet, use the TextBlob library. Perform the following steps for each tweet:

```
analysis = TextBlob(tweet.text)
print(analysis.sentiment)
print("")
```


b. Saving tweets and their sentiment to a CSV file:
Instead of printing each tweet's sentiment, you can save them to a CSV file with corresponding labels ('positive' or 'negative'). You can decide the sentiment polarity threshold yourself. Add the following code inside the loop:

```
sentiment = analysis.sentiment.polarity
if sentiment > 0:
    label = 'positive'
else:
    label = 'negative'

with open('tweets.csv', 'a') as file:
    file.write(f'{tweet.text},{label}\n')
```


### Conclusion:

The completed code should consist of approximately 40-50 lines, including the necessary imports, authentication, tweet retrieval, sentiment analysis, and saving of tweets to a CSV file. This project will provide a practical introduction to using machine learning techniques for sentiment analysis in Python, utilizing the Tweepy and TextBlob libraries. Intermediate coders will gain hands-on experience in retrieving data from an API, performing sentiment analysis, and storing results in a CSV file.
