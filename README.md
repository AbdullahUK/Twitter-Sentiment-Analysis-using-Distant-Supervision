# Twitter-Sentiment-Analysis-using-Distant-Supervision
Twitter is a popular microblogging service where users create status messages called “tweets”. These tweets sometimes express opinions about different topics. We introduce an approach for automatically classifying Twitter messages to either positive or negative for English and Arabic tweets.
# Approach 
Our approach is to use different machine learning classifiers and feature extractors as well as Artificial Neural Networks (ANN). The machine learning classifiers are Logistic Regression, Naive Bayes,, Multinomial NB, Ridge Classifier, Passive-Aggressive Classifier and Support Vector Machines (SVM). The Artificial Neural Network is used along with Tfidf vectorizer The feature extractors are unigrams, bigrams and trigrams. We built a framework that treats classifiers and feature extractors as two distinct components.
# Dataset Description 
0 — the polarity of the tweet (0 = negative, 2 = neutral, 4 = positive)</br>
1 — the id of the tweet (2087)</br>
2 — the date of the tweet (Sat May 16 23:58:44 UTC 2009)</br>
3 — the query (lyx). If there is no query, then this value is NO_QUERY.</br>
4 — the user that tweeted (robotickilldozr)</br>
5 — the text of the tweet (Lyx is cool)</br>
# Preprocessing 
 <li> Emoticons as ":), :(, :-), :-(,:D, =)" are stripped off. This is important for training purposes. If the emoticons are not stripped off, then some classifiers tend to put a large amount of weight on the emoticons, which hurts accuracy.</li>
 

<li> Any tweet containing both positive and negative emoticons are removed. This may happen if a tweet contains two subjects. Here is an example: Target orientation :( But it is my birthday today :). These tweets are removed because we do not want positive features marked as part of a negative tweet, or negative features marked as part of a positive tweet. </li>
 
<li> Retweets are removed.This usually happens if a user likes another user’s tweet. Retweets are commonly abbreviated with “RT.” For example, consider the following tweet: Awesome! RT @rupertgrintnet Harry Potter Marks Place in Film History http://bit.ly/Eusxi :). </li>
 
<li> Tweets with “:P” are removed. As the Twitter API has an issue in which tweets with “:P” are returned for the query “:(”. These tweets are removed because “:P” usually does not imply a negative sentiment.</li>
 
 <li> Repeated tweets are removed. Similar to retweets, duplicates are removed to avoid putting extra weight on any particular tweet</li>
 
<li> Converting  HTML encoding to text</li>
 
<li> Replacing any url with class URL</li>
 
<li> Replacing any @username with class USERNAME</li>
 
<li> Striping  repeated chars. For example “Huuuuugry !” becomes “Huungry !”</li>
 
<li> Replacing #hashtag with hashtag</li>
 
<li> Removing Numbers</li>

# Results for English tweets
<li> The best result we can get with logistic regression was by using TFIDF vectorizer of 100,000 features including up to trigram .Validation accuracy is 82.73%, while train set accuracy is 84.18%
</li>
<li> Training tfidf vector with a Neural Network of 100k features, using 20% dropout gave validation accuracy of 82.58% and train set accuracy of 84.26%
</li>

# Results for Arabic tweets
<li> Using the Logistic Regression classifier, the best validation accuracy scored was 78.7% which is lower than that of the English dataset.
</li>
<li> Using the same architecture of the ANN used for the English dataset, it produced much better results on the Arabic dataset, scoring nearly 87.6% validation accuracy which is significantly higher than any accuracy reached in the English dataset
</li>
