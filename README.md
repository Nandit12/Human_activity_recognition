# Human activity recognition using smartphone (simplest)
Analysing intermediate dataset Human activity recognition using smartphones and building a multi classification model.
you can download the dataset here:-https://www.kaggle.com/uciml/human-activity-recognition-with-smartphones . The overview of the whole data is given in the link.

## Result :
Achieved an accuracy of 94% to predict between 6 categories with 561 features.
It's amazing we can differential between standing and sitting and reaching 94% accuracy.

## Overview :
The is the simplest method to achieve best accuracy with relevant results and proper evaluation of it. Done in jupyter notebook.

## Short summary of data :
The data contains 561 features with the task to predict between 6 categories i.e. sitting, standing, walking, walking upstairs, walking downstairs and laying. The features are generated with only two sensors (accelometer and gyroscope) which are in time and frequency domain.

## Preprocessing :
The data is imported as dataframe using pandas. It is then checked for null values. All the categories are converted to numerical values as {'Activity': {'LAYING': 1, 'SITTING': 2, 'STANDING': 3, 'WALKING': 4, 'WALKING_DOWNSTAIRS': 5, 'WALKING_UPSTAIRS': 6}} . This is done  for both train and test data. The data is then splitted as X_train, y_train, X_test, y_test. (features and target for both train and test).

## Choosing the right model for training the data:
From our knowledge of data we can deduce which model to use for training the data. Here for this data we will use SVM as our model because the data has lots of features (561) and lots of categories to predict (6). If you wish to use Logistic regression, KNN or other models you will not get this much accauracy because they fail to differentiate between the categories sitting and standing (these activities are almost identical). Why this happens? Because Logistic regression only classifies data in a 2-d plane therefore fails to predict for multi classification problem. For KNN it utilizes distance as its metrics to classify data (here it is hard to classify between sitting and standing). Why SVM is better here? Because it classifies in a multi-dimensional plane which is best for multi classification.

## Training :
The SVM model is trained and prediction is stored in yhat. 

## Evaluation :
Confusion matrix is used to evaluate how well our model performs. This tells us that model is quiet well in predicting all categories (94%). F1 score and jaccard similarity score is used for cross checking. The result is same.
