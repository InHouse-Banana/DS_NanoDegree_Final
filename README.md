# Data Science NanoDegree Final Project: Sparkify

This is the final project for the Data Science Nanodegree.

## Motivation 

This repository address the question: given a dataset containing the user activity in Sparkify, a music streaming service, is it possible to predict which users will churn?

## Methodology 

Due limited computational resources, only a subset of the total data was used. Though the procedures here described should be valid to the overall dataset.

First of all churn was defined as those users that visited the website: Cancellation Confirmation. With this in mind the original dataset was cleaned and transformed into useful features:

1. lifetime: time in the service before cancelling 
2. total_songs: total songs listened
3. num_thumb_up: number of thumbs up given in the service
4. num_thumb_down: number of thumbs up given in the service
5. add_to_playlist: total number of songs added to playlists
6. add_friend: number of friends added
7. avg_songs_played: average number of songs listened per session
8. gender: gender

Then a pipeline was introduced to perform feature scaling (using a standard scaler) and then model fitting using CV without any parameters to try. In this step, he metric used to determine a model's fit was Accuracy and F1, due to the imbalance in the output classes (churned vs not churned)

The different models tests with their default settings are as follows:

1. Logistic Regression
2. Gradient Boosted Trees
3. Random Forest 
4. Decision Tree Classifier

After which the best one was selected and further tuned. The conclusions are based on such model.

## Results 

Given the features processed it was found that the best model to further test was the Logistic Regression with an Accuracy: 0.756 and an F-1 Score:0.734. 

Further tuning lead to overfitting in the training set, which lead to Accuracy: 0.782 and F-1 Score:0.698. Most likely due the small size of the data.

In terms of the feature importance, the most relevant are, in order,  'num_thumb_up', 'total_songs',  'lifetime'.

## Outlook and improvements:

There are several aspects of this analysis that could be expanded and that could change dramatically the outcome. 

1. full dataset: the sample used is a less than 1% of the total dataset (12gb) thus the conclusions showed here are of limited validity
2. numFolds: related with 1. in this case the number of folds was set to 3, but with larger datasets this could be increased to 10
3. features: more categorical features could be used

## Files

1. mini_sparkify_event_data.rar
2. README.md
3. requirements.txt
4. Sparkify.ipynb

## Requirements
1. matplotlib==2.1.0
2. pyspark==2.4.3
3. seaborn==0.8.1
4. python==3.6.3