# Project 3 - Subreddit webscraping

## Problem Statement:

Reddit is a platform that is a social news aggregator, web content rating, and discussion website. In the platform there are many subreddits which are smaller forums of any particular topic. In each topic the user has the ability to create a post about the particular subreddit they are in. the goal of my project is to choose two particular subreddits. With these two forums chosen i would webscrape both subreddits in order to collect my data. With the data collected i will ultimately be able to model and predict which post post belongs to which subreddit. Using the past data cleaning techniques as well as new ones to help create a better model. the models with range from logistic regression and naive bayes to more recently implemented decision trees and random forests. With the implementation of pipelines and grid searches we would now be able to test our models over a variety of different conditions.  

# Executive Summary:

## Data 

The data collect originated from two subreddits: artificial and MachineLearing. The subreddits share very much in common when it comes to topics and discussions. After collecting the data our focus will be primarily on two categories. One will be the tile of every topic. The second will be the body or text of that topic. Using prior webscarpping techniques only resulted in a maximum of 1000 entres with most being duplicates of past posts. This not only made cleaning the data result in a small set of entries but also reduced the overall amount of data to train from. Instead in order to collect the large quantities of data, usually 1000’s of posts, we would rely on pushshift. Pushshift is a big-data storage project started and maintained by Jason Baumgartner. With pushshift.io we no longer need to web scrape from reddit but itead query the posts we need form pushshifts data storage. Which gave us the data in the format we needed.
## Cleaning

WIth the data now gathered i began organizing and preparing the data to be used for modeling. What that included was putting the data into a dataframe. During this time I removed any duplicated that could be found as well as posts made by an auto generated bot that would create the same message and title in each subreddit. Finally I removed any posts that had an empty body. Other then dropping a few columns that were not necessary, these were the only things removed from the dataset. 

Then we move on to the posts themselves. We split each string into different chunks that are then saved whether they meet a certain criteria of the tokenizer. Html links/tags removed from the text before being tokenized. Afterwards the strings are converted to lowercase so that they can be easily comparable to the other subreddit later on. The next step in the process is to remove stop words. Stop words are usually very common words that for the most part do not add any more information but does create a larger dataset then needed. By removing them the message of the string is not lost and performance is improved. We then run each string through lemmatization/stemming to gain the root word. This ends the portion of data cleaning and manipulation. 
## Features

| Features | Type   | DataSet | Description                           |
|----------|--------|--------|----------------------------------------|
| Title    | String | Reddit | Title of the post in the sub-reddit    |
| SelfText | String | reddit | The body of the post in the sub-reddit |

## Modeling 

Using CountVectorizer and TfidfVectorizer separately pushed the X_train through various models. These models included logistic regression, Naive bayes, gassan Bayes, and decision trees. Through these various models I found that logistic regression performed the best out of the various models but also had a .05 drop from training to text score. Showing that the model is a bit overfit compared to the others. Trying out the other models demonstrated that depending on your data some models might perform better than others as I noticed other individuals in my class had better results with other further models. I would need to compare my logistic results to something like random forests to see if that could improve my accuracy score. I would find that this would be the perfect situation to implement cloud computing as the use of different parameters with pipe in gridsearch causes longer run times. 

## Conclusion


