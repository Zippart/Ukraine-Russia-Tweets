## In progress

## Purpose:
Topics modeling and named entity recognition can help people understand key figures and events. This in turn can help humanitarian organizations locate areas of importance. It can help them understand the scope of conflict and impact. Models trained on this current dataset can become more effective at retrieving future relevant information. Organizations can gain insight into the evolution of political discourse and humanitarian response historically to make future informed decisions.


## 1.	Data
https://www.kaggle.com/datasets/bwandowando/ukraine-russian-crisis-twitter-dataset-1-2-m-rows

These are Kaggle datasets contain tweets monitoring the current ongoing Ukraine-Russia conflict gathered from the Twitter API as of June 16. All accounts have been stopped due to new API migration. 
There are around 20 million rows of Twitter user data, 1.5 million rows of tweets, and 1 million rows of English language tweets.

## 2.	Method
I tried two different k-means clustering, 11 kmeans and 5 kmeans. Neural networks are being considered for future development.

## 3.	Cleaning
By virtue of grabbing English only tweets, I was able to get no null values. The value counts were fine. After unsupervised learning clustering, two rows of null values were missed.

## 4.	EDA
I needed to check out my data overall with a pretrained NER model, and then I also used a pretrained NER model to look for unique entities between clusters.
I initially used said model to generate entities, labels, and their counts.
I looked at just the text from the csvs because I’m focused on manipulating that data only. I initially thought I’m not interested in who posted or where it came from or other columns. But in hindsight, should’ve considered the date of the tweets at least. Could’ve compared the tweet clusters by time.
After making a 5 kmeans and 11 kmeans cluster model, I used another NER model to see which clusters are what.

## 5.	Machine Learning

## 6.	Recommendations

## 7.	Future Improvements

## 8.	Credits

Thank you to everyone in the Springboard Slack and my mentor that helped me navigate this project!
