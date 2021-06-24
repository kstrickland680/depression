# Depression Classification 

## Overview
This project analyzes depression data from a survey, found here: https://www.kaggle.com/francispython/b-depression

I explore the data looking for correlations between various data points and depression. Major depression disorder is among the most prevelant mental disorders in the United States. It is diagnosed when a person experiences depressed mood for at least 2 weeks, combined with certain specfied symptoms which shows problems with biological functioning and ability to enjoy life.

## Business Problem

A mental health agency is interested in if there's a way to check for depression in clients based on survey results. They're also curious about what survey questions to pay attention to as either risk factors or protective factors for depression. 

## Correlations

There may be some relation of school attendance as a protective factor. Most elements by themselves do not seem to be strongly correlated with depression.

With the XGBoost model, no variable by itself has a strong correlation with depression. However, some of the variables that do rank highest are asset_phone, med expenses, own farm, fs_adwholed, not having mpesa, and having asset savings. 

![picture](https://github.com/kstrickland680/depression/blob/main/images/assets.JPG)
![picture](https://github.com/kstrickland680/depression/blob/main/images/netmpesa.JPG)
![picture](https://github.com/kstrickland680/depression/blob/main/images/parent.JPG)


## Models

Creating a classification model for this data set was difficult and did not create results with good recall or precision. 

First I attempt a KNN model. However, it has very low recall and F1 scores. I check multiple K values but am unable to find one that allows the model to perform well. 

I create a Random Forest Classifier and hypertune the values of max depth, min samples split, and min samples leaf. However, this model doesn't work at all. Despite the grid search being told to prioritize recall scores, the model has a 0% recall. 

The decision tree model also goes from a low recall score to not predicting depression at all. I perform a grid search to hypertune the values of max depth and min samples split to help improve overfitting and recall scores.  However, the validation recall score is 18.92% and the difference between training and validation recall scores is 26.94%. I then hypertune the min samples leaf paramater, and the recall score goes to 0%. This model also doesn't work. 

At first XGBoost Model seemed promising, but it overfits the data. I perform several gridsearches to help with the overfitting, including looking at max depth, min child weight, gamma, subsample, colsample by tree, and learning rate. The model continues to overfit the data, but unlike previous attempts, at least the recall score never becomes 0. 

## Recommendations

With the XGBoost model, no variable by itself has a strong correlation with depression. However, some of the variables that do rank highest are asset_savings, med expenses, own farm, fs_adwholed, not having mpesa, and having asset savings. The company should look closely at individuals who don't have savings or are struggling financally, individuals without children and individuals with high medical expenses. 



## Conclusions

This data was difficult to create an accurate and useful model for due to missing values and few entries for depression. Depression is a complex condition, so it makes sense that creating a model to predict it would be equally complex.  It was also difficult with the given values to find values highly correlated with depression.  

Having children seems to be a protective factor. Individuals without savings or with high medical expenses seem to be at higher risk for depression.  

To continue researching this, data needs to include a greater number of depressed clients. Future surveys could measure more social areas as well as individual's perception of quality of life, including having clients rate the quality of their social life, family relationships, financial stability, job happiness, as well as education level, race, gender identity, and age.  

## Future Work

Future work can focus on exploring more data, especially of depressed individuals.  It could explore the correlations of perception of family relationships, social relationships, and financial stability with depression.  It would also be interesting to look at whether having friends who are depressed impacts an individual's likelihood of having depression. With more data and categories, I would want to create a scale based on the results that would look at the likelihood for depression based on various aspects of their life.  I'd also continue tuning the model to decrease overfitting and improve the recall scores. 

