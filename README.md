# Movie_Recommender_Service
### Seattle University - Big Data Analytics
### Author: Jennifer Grosz


## Business Problem
A new startup business, Ripe Pumpkins - a movie review-aggregation service, would like to implement Pumpkinmeter, a measurement of collaborative recommendation for millions of fans. The board of directors have been convinced by the recent success of recommendation model in streaming services and would like to know the potential in the Ripe Pumpkins' new initiative, Pumpkinmeter score. For this exercise, we will use the data collected by GroupLens. 

GroupLens Research has collected and made available rating data sets from the MovieLens web site (Links to an external site.). The data sets were collected over various periods of time, depending on the size of the set. They can be found here (Links to an external site.).

In our case, we will use the latest datasets (data size is subject to change):

Small: 100,000 ratings and 3,600 tag applications applied to 9,000 movies by 600 users. Last updated 9/2018.
Full: 27,000,000 ratings and 1,100,000 tag applications applied to 58,000 movies by 280,000 users. Includes tag genome data with 14 million relevance scores across 1,100 tags. Last updated 9/2018.
In Collaborative recommendation (collaborative filtering) we make predictions (filtering) about the interests of a user by collecting preferences or taste information from many users (collaborating). The underlying assumption is that if a user A has the same opinion as a user B on an issue, A is more likely to have B's opinion on a different issue x than to have the opinion on x of a user chosen randomly.

## Analysis
In order to build an on-line movie recommender using Spark, we need to have our model data as preprocessed as possible. Parsing the dataset and building the model every time a new recommendation needs to be done is not the best of the strategies.

The list of task we can pre-compute includes:

Loading and parsing the dataset. Persisting the resulting RDD for later use.
Building the recommender model using the complete dataset. Persist the dataset for later use.
Spark MLlib library for Machine Learning provides a Collaborative Filtering (Links to an external site.) implementation by using Alternating Least Squares (Links to an external site.). The implementation in MLlib has the following parameters:

numBlocks is the number of blocks used to parallelize computation (set to -1 to auto-configure).
rank is the number of latent factors in the model.
iterations is the number of iterations to run.
lambda specifies the regularization parameter in ALS.
implicitPrefs specifies whether to use the explicit feedback ALS variant or one adapted for implicit feedback data.
alpha is a parameter applicable to the implicit feedback variant of ALS that governs the baseline confidence in preference observations.

## Communication
The board like to explore if the recommendation engine yield insights of individual customer's preferences that eventually affect customer's likelihood stay with our services than competitors' services.

Your task will be to prepare data insights/foresights that will be part of the CEO's presentation at the board's next meeting. Your presentation should show the results from two test sets with two scenarios:

Apply two new users (i.e., yourself, and a friend/family member) with each person’s ratings of 10 movies (use the section, Adding new user ratings). You need to run one user at a time.
Generate top 15 recommended movies for each user
Scenario 1 - FULL dataset, filtering out movies with less than 25 ratings
Scenario 2 - FULL dataset, filtering out movies with less than 100 ratings
In summary, you need to run 4 cases to get all results:
User 1 - Scenario 1
User 1 - Scenario 2
User 2 - Scenario 1
User 2 - Scenario 2
Interpret the results and provide Insights/Foresights on both scenarios
In addition, you should prepare both a presentation file (pptx) and a comprehensive case report (docx) to the board along with your project files (Jupyter html and ipynb). 


## Presentation
![Movie_Recommender_Presentation.pdf](https://github.com/JenniferGrosz/Movie_Recommender_Service/blob/e67b632293270fd395e83582a65583a5370b048e/Movie_Recommender_Presentation.pdf)


## Project
![Movie_recommendation_service.pdf](https://github.com/JenniferGrosz/Movie_Recommender_Service/blob/3e96c89ee3c732f3edc2d503f038dd2bbf512f93/Movie_recommender_system.pdf)
