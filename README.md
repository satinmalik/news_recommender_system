# news_recommender_system
## Problem Statement
iPrint is an upcoming media house in India that offers media and information services to the people. The company’s business extends across a wide range of media, including news and information services on sports, weather, education, health, research, stocks and healthcare. Over the years, through its online application, iPrint has been efficiently delivering news and information to the common people.  However, with time and technological advancements, several new competitors of iPrint have emerged in the market. Hence, it has decided to begin providing a more personalised experience to its customers.

 

Till date, iPrint was managing its customer base by only recommending the most popular and similar news articles to what the user has already read or watched. However, the recommended news articles were often not relevant to the majority of the users. It was not able to recommend any new content to its customers, and gradually, the company started losing such users, which eventually resulted in immense revenue loss. 

 

iPrint being a cutting-edge company, is trying to solve this issue of revenue leakage by personalising user tastes and introducing new content to its users at the start of the day on the home page of the application. iPrint is planning to assess these recommendations by tracking whether the user clicks on those items or not. Moreover, once the user clicks on any news item A, it wants to recommend news similar to the news A, at the bottom of the page of the news item A. 

 

Now, let's understand what iPrint is trying to achieve here. By, recommending new items to the users at the start of the day, it is trying to understand if the user has new interests or not. Now, if the user clicks on the new item A and then also on subsequent items recommended at the bottom of the news item A, then iPrint can infer that the topic/ genre of the new item is something of user interest.

 

Now, you have been hired as a data scientist to help iPrint build a robust product to achieve its new objectives. Using the expertise acquired through the program, along with the learnings of the previous session, you need to build a system that would recommend relevant news articles to the customers based on their search history and preferences. 

 

So the problem statement can be divided into two parts discussed below. Of the numerous news articles available on its app about sports, politics, technology and many others, iPrint wants you as a data scientist to identify and build an appropriate recommendation system that would:

Recommend new top 10 relevant articles to a user when he visits the app at the start of the day
Recommend top 10 similar news articles that match the ones clicked by the user. Try different models for generating these recommendations and experiment with hybrid models for the same
You have to ensure that the system does not recommend any news article that has been pulled out from the app or has already been seen by the user. In addition, only the articles that are written in the English language must be considered for content-based recommendations. The final generated list must contain the names of the recommended articles, along with their IDs.

 

You can download the data set from the zip file attached below.

Capstone Dataset
Download
Data Dictionary:

Please refer to the following data dictionary for a better understanding of the features.

 

consumer_transactions: It contains the details of the transactions of the customers on the platform.

Features	Description
event_timestamp    	Timestamp at which the user interacted with the news articles.
interaction_type    

Type of interaction made by the user: content_commented_on/ content_followed/ content_liked/ content_saved/ content_watched

item_id	
ID of the item with which the user interacted 

consumer_id  	ID of the consumer who interacted with the item
 consumer_session_id    	
ID of the session during which the user interacted with the item

consumer_device_info    	Information about the device used by the consumer
consumer_location    	Location of the consumer
country	Country of the consumer

platform_content: It contains the details of the news articles present on the platform.

Features	Description
event_timestamp	Timestamp at which the interaction happened
interaction_type	Type of the interaction - content present/pulled out
item_id    	ID of the item on the platform
producer_id	ID of the producer
producer_session_id	ID of the session when the producer interacted with the item
producer_device_info    	Information about the device used by the producer
producer_location	Location of the producer
producer_country	Country of the producer
item_type	Type of item on the platform - HTML/VIDEO/RICH
item_url	URL of the item
title	Title of the content
text_description	Description of the content
language	Language of the content on the platform
                    


You can learn more about the data set in the next video.

Play Video2255004
Procedure:
Though you can approach the problem any way you wish, a simple process has been outlined for you below:

 

Data pre-processing

The data set provided to you does not contain user ratings that could be used to generate recommendations. For that you need to impute the rating values based on the feature ‘interaction type’ with the highest weightage to content_followed, followed by content_commented_on, content saved, content liked and content_watched. The final data set ‘consumer_interactions’ that will be used to build the recommendation system should contain a feature called ‘ratings’ along with other features that are required to build the ALS, user-based and item-based collaborative filtering models.

 

Use the ‘platform_content’ data to extract the data set that contains the English articles present on the platform.

 

Exploratory data analysis

Explore the various features present in the data set for their distribution and any meaningful inferences.
Check the distribution of interaction type, consumer location/country, producer country/location, item type and so on.
Check the most common language and most popular country that consumes the articles on the platform.

Recommendation techniques

You may want to use the ‘consumer_interaction’ data set for building the ALS, user-based and item-based collaborative filtering models and ‘platform_content’ data to build a content-based recommendation model.


User-based collaborative filtering

Create user-item matrix using the rating values.
Find the user-similarity matrix based on a similarity measure.
Generate predicted ratings for all the user-item pairs.
Item-based collaborative filtering

Find the item-similarity matrix based on a similarity measure.
Generate the top 10 similar and relevant items based on the similarity scores.
Content-based filtering

Use text processing to analyse the ‘keywords’ feature in the data set.
Recommend similar items based on the TF-IDF scores.
ALS

Create Compressed Sparse user-item and item-user matrices. 
Train the ALS model and generate recommendations for a user. Try experimenting with the hyperparameters.
Hybrid recommendation system

Normalise the scores for content and collaborative filtering and combine them with an appropriate weightage to build a hybrid model.
Try out hybrids of different types of models that can help recommend items similar to a particular item. For example, Content+Item-based collaborative model, ALS+Item-based collaborative model, ALS+Content-based model, etc.
Model evaluation

Use appropriate evaluation metrics, such as RMSE, MAE and precision@k, to evaluate the recommendations generated for a user as mentioned in the first part of the problem statement and use global precision@k to assess the overall performance of the recommendation system.

 

Also, recommend appropriate evaluation techniques for the second problem statement. This is an open-ended question and you can explore the different techniques that are available for online evaluation and give your thoughts on it. You need not come up with the ones which are already covered in the module.
