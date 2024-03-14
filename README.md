# mbti_predictor
Building of a pre-trained model that retrieves information from language and predicts personality type. 

In this repository, you will find a folder names "datasets" which contains the data used for training the model. 

The full dataset was built from a kaggle entry, which contains tweets from different users and labels that indicate their personality. The original dataset can be found here: https://www.kaggle.com/datasets/mazlumi/mbti-personality-type-twitter-dataset/data

As this model is aimed to predict personalities in the Spanish language, which here can be considered a low-resource language with no available datasets similar to the one we used, our solution was to translate the data from English to Spanish by using the Deepl API. The script for this initial task can be found in "translations.ipynb". 

For information retrieval of the texts, we initially computed a sentiment analysis of the translations by using the sentiment_analysis_spansih library. A sample of this can be seen in the "mbti_feature_ex.ipynb" file, which uses the "raw_datasets" data to compute this value.

Thus, our final datasets for the predictive model include information about the original tweet, translation, sentiment analysis and label (personality type). 

The predictive model is stored in the "mbti_model.ipynb" file. 

This is not a complete model, what you will see is an initial fit that tests how it initially performs with the data provided. We expect to continue retriving information from the translated texts in order to add more numerical data to every vector that represents each training data point. We also want to scale this model into classifying into the four main categories of the MBTI model (NF, NT, SF, ST). Our model currently attempts to perform a binary classification between the NT and SF classes, which could be seen as opposites, we aim to scale this into a multi-class classification. 
