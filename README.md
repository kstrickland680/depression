# Depression Classification 

## Overview
This project analyzes depression data from a survey, found here: https://www.kaggle.com/francispython/b-depression

I explore the data looking for correlations between various data points and depression. Major depression disorder is among the most prevelant mental disorders in the Unitd States. It is diagnosed when a person experiences depressed mood for at least 2 weeks, combined with certain specfied symptoms which shows problems with biological functioning and ability to enjoy life.

## Business Problem

A mental health agency is interested in if there's a way to check for depression in clients based on survey results. They're also curious about what survey questions to pay attention to as either risk factors or protective factors for depression. 

## Correlations

There may be some relation of school attendance as a protective factor. Most elements by themselves do not seem to be strongly correlated with depression.

With the XGBoost model, no variable by itself has a strong correlation with depression. However, some of the variables that do rank highest are asset_phone, med expenses, own farm, fs_adwholed, not having mpesa, and having asset savings. 

![picture](https://github.com/kstrickland680/depression/blob/main/images/parent.JPG)
![picture](https://github.com/kstrickland680/depression/blob/main/images/depassets.JPG)

## Models

Creating a classification model for this data set was difficult and did not create results with good recall or precision. 

## Conclusions

This data was difficult to create an accurate and useful model for due to missing values and few entries for depression. Depression is a complex condition, so it makes sense that creating a model to predict it would be equally complex. It was also difficult with the given values to find values highly correlated with depression.

Having children seemed to be a protective factor.

To continue researching this, data needs to include a greater number of depressed clients. Future surveys could measure attributes including having clients rate the quality of their social life, family relationships, financial stability, job happiness, as well as education level, race, gender identity, and age.

