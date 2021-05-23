# SF-crime-classification
This is a project from Kaggle: SF crime classification\
https://www.kaggle.com/c/sf-crime/overview \
I have tried to visualise and analyze San Francisco crime data and predict the type of crime using time features and spatial fetures. 

Key steps:
1. Data Exploration
- although there are no missing values in train/test set, the coordinates features X and Y contain mistakes values that are outside San Francisco
2. Data Visualisation
- plot histogram to see the distribution of each crimes in different police district/month/year ...
3. Feature Engineering
- extract year, month, day, hour from 'Date'
- extract street type, intersection/block from 'Address'
- use k means clustering to divide SF into 36 subareas according to coordinates
- generate new feature 'PsDistrict' from coordinates to show the shortest distance to the nearest police station
4. Modelling
- baseline model is to predict all crimes in test set to be "Larceny/Theft", which is the most frequent crime type in train set
- use logistic regression / knn / xgboost, all have improved compared to the baseline model
- use hyperparameter tuning to find the optimal n_neighbors from knn, max_depth/learning rate for xgboost
5. Result
- log loss 2.42609, approximately ranking #603 out of 2331

Questions for future:
1. Data visualisation should be an indicative guidance for the following feature selection/engineering, but my visualisation doesn't feel very useful
2. Hyperparamters tuning, even with RandomizedSearchCV, is extremely slow, is there any better method to speed up the process

Reference:
- https://github.com/k-chuang/kaggle-sf-crime#visualizations 
- https://www.kaggle.com/impratiksingh/sf-crime-classification-beginner-tutorial 
- these 2 notebooks are wonderful guide for data science beginners 
