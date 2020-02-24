# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 3: Web APIs & NLP

## Problem Statement - MLS Expansion into Europe

I currently work in the marketing department of the MLS and as part of our new expansion plan into Europe, we are looking to roll out a new marketing campaign by searching through peoples social media and hashtags as a means growing the popularity of the MLS. In Europe however, Football means both Soccer and American Football due to the increasing expansion of the NFL overseas. Can I building a predictive model using the NFL and football reddit's to distinguish which type of football people are talking about and reach out to the ones interested in watching football?

We will run various classification models during our testing such as Bayes Classifier, Logistic Regression, KNN, and Decision Tree's. To score these, we will be looking at Accuracy as a means of scoring and determining which model we will be selecting here.

##  Executive Summary
When being tasked with this project, I had to go out on our own and find two
different subreddit pages: one that talked about Football and one that talked about American Football. Browsing through the football community for a page to use, I was able to settle upon the football subreddit on one page that we would be able to pull information. When it came to finding the American Football subreddit, I was unable to use their page due to the inappropriate language that I was reading through when it came to the titles. I then decided it would be best to use the NFL page as a means of me gathering my data. From there, we were able to pull the information through the API that subreddit has to offer and extract the text we were looking for in a concatenated Data Frame (df).

After creating our df, we then had to start our cleaning process of dropping unnecessary columns as well as cleaning up our text. We started by dropping columns that had unnecessary features as well as any duplicates that were in the dataset. This then brought us to 6 columns that I believe can add value to our dataset. After lowering, splitting, and Porter Stemming our Dataset, we then had a Data set that was ready to be analyzed. We looked at most common words through our Count Vectorizer and which words were important in our Tfidf Vectorizer. After gaging what words stood out, we were ready to run our models and evaluate the data given. 

## Data

### Data Sets:

For our Data sets, we had to scrap comments from subreddits on Reddit.com.

- [Football Reddit](.https://www.reddit.com/r/football/)
- [NFL Reddit](.https://www.reddit.com/r/nfl/)

### Data Dictionary

|Feature|Type|Dataset|Description|
|---|---|---|---|
|**title**|*Object*|Final Data Frame|Comment in post being made|
|**selftext**|*Object*|Final Data Frame|Text that doesn't link outside of reddit|
|**subreddit**|*Object*|Final Data Frame|Community within reddit|
|**author**|*Object*|Final Data Frame|Person who is publishing post within subreddit|
|**num_comments**|*Integer*|Final Data Frame|How many comments the post gathered.|
|**timestamp**|*Object*|Final Data Frame|Date of the post|
|**clean_title**|*Object*|Final Data Frame|Title words after being cleaned and Porter Stemmed|


## Conclusions

In conclusion, we can say that we were able to build a good model based on key words being used in both reddits. We were able to show a high bias train score along with a very low variance when evaluating that against our test. As we look at our coefficients, we we were able to see several words that, when exponentiated, will tell us how many times likely a word is to appear in that subreddit. When looking at the top ten for each, words you would expect to associate with each sport were there but he most interesting find from this was the word 'happy'. Happy had a coefficient of ~3.03, and when exponentiated, we found out that people using the word happy will be 20.7 times as likely to be talking about football rather then the NFL. When evaluating our Confusion Matrix, several key stats stood out to us:
- Accuracy:
    88.1%
- Misclassification:
    11.9%
- Sensitivity:
	82.8%
- Specificity:
	91.5%

With these measurements, we can see how accurately our prediction were against the model we built. We can say we were 88% accurate in predicting the words that went into both the NFL and Football bucket where we misclassified ~12% of them. We can also state that our True positive which represent the words that were actually correlated to football subreddits and they predicted to be part of the football subreddits, scored at a 82.8% accuracy based on all the predicted values that predicted to be in the football subreddit.

## Recommendation

Going forward, the model will fairly predict well and can be implemented to score at a high rate. However, based on the fact that we were only able to pull an estimated 4,700 data points, I don't believe we are ready to roll out this model yet. I would like to first analyze the selftext column that we pulled to see if there are possibly some key words in there that can be pulled. I also believe we should keep searching for various other blogs/ post to see if the same words keep popping up and cross validate those against each other. Once we gain confidence on the key words being used in social media post to see which type of football people are talking about, then we can roll out our model to market.

### References:
https://www.reddit.com/r/football/
https://www.reddit.com/r/nfl/
https://www.nielsen.com/us/en/insights/article/2019/football-fever-is-spreading-as-major-league-soccer-kicks-off-a-new-season/
https://www.schneiderdowns.com/our-thoughts-on/growth-of-soccer-in-america
