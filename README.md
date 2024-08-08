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

![image](https://github.com/user-attachments/assets/e7d85899-d952-46c4-b3d6-acf7bd8ad0e7)
![image](https://github.com/user-attachments/assets/cc9f5e36-8bb9-4ad5-bdb1-b5c56522b370)
![image](https://github.com/user-attachments/assets/4fa11bf0-3f14-4550-a734-cd4214d3e986)


## 5.	Machine Learning
After making a 5 kmeans and 11 kmeans cluster model, I used another NER model to see how my data was clustered. When graphed, there was a distinct cluster that is unique from the others. 
5 kmeans was just a starting point for params. But it ended up being sufficient enough. The other parts were default:
-	k-means++ for centroids
-	n_init – number of algorithim runs
-	etc…

My 5 kmeans model had a DBI (Davies-Bouldin Index) score of 2.7, and my 11 kmeans had a 9. I used hyperparameter tuning to arrive at an 11 kmeans model, but it somehow performed worse. Also, when graphing both, I could not discern a meaningful difference. This is likely because most of the clusters were unfortunately closely knit and interspersed with each other. Other accuracy metrics to compare the two kmeans like silhouette scores and Calinski-Harabasz Index I couldn’t code properly. 

![image](https://github.com/user-attachments/assets/599aa5b4-4cf2-47ca-99f1-ba0d74220291)

## 6.	Recommendations
A web application could be developed to show the amount of popularity certain entities have to gauge varying degrees of importance through a GUI from the dataframes created from the different clusters.

It may be a bit messy, but the unique entities amongst the two groupings of clusters (comparing clusters 0-2 and 0-5), provide a good number of entities to explore. The business problem revolved around: “identifying key figures, events, and areas of importance, which will improve the ability of humanitarian organizations to understand the scope and impact of the conflict”. And I believe looking through the entities can help with that.

![image](https://github.com/user-attachments/assets/b6fa2c45-61f7-4f49-bbca-f2e0efb8fcf7)
![image](https://github.com/user-attachments/assets/f9a7239a-cc78-4caf-b9e0-821b65f482a4)
![image](https://github.com/user-attachments/assets/f1daaad2-fa1a-4644-855c-f9e9173d2602)


## 7.	Future Improvements
Including geographic location, the timing of tweets, and sentiment analysis could help in identifying trends and serious points of conflict. As mentioned earlier, neural networks are being considered, in addition to getting other accuracy metrics to work. Lastly, I need to test the clustering models on unseen data.

## 8.	Credits
Thank you to everyone in the Springboard Slack and my mentor that helped me navigate this project!
