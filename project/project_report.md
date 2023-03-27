# Report: Predict Bike Sharing Demand with AutoGluon Solution

## Initial Training

### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?

Answer: I fixed some syntax errors and installed "tablulate" in order to successfully import "TabularPredictor". I did all parts of my project in Amazon SageMaker Studio and submitted the results on my Kaggle account.

### What was the top ranked model that performed?

Answer: Top ranked model WeightedEnsemble\_L3 with hyper parameter optimized

## Exploratory data analysis and feature creation

### What did the exploratory analysis find and how did you add additional features?

Answer: Time series analysis showed that:

- The last 10 days of the month have missing data. i.e. starting on the 20th;
- The variations in demand at each hour of the week and on weekends.

I decided to split the "datetime" into year, month, day and hour in order to improve the performance of model.

### How much better did your model preform after adding additional features and why do you think that is?

Answer: Approximately 36%. If we adjust some of independent variables ("seasons", "working\_hours", and etc ) in our model, performance of our model'll increase.

## Hyper parameter tuning

### How much better did your model preform after trying different hyper parameters?

Answer: Model performed better after trying hyperparameters.

### If you were given more time with this dataset, where do you think you would spend more time?

Answer: Data preprocessing, feature engineering and hyper parameter tuning.

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.

| **model** | **hp-method** | **score** |
| --- | --- | --- |
| **initial** | none | **1.80805** |
| --- | --- | --- |
| **add\_features** | regression | **0.68137** |
| **hpo** | autogluon | **0.56331** |

### Create a line plot showing the top model score for the three (or more) training runs during the project.

TODO: Replace the image below with your own.

![](RackMultipart20230121-1-5f87sc_html_9a7c4164ad2f7ed1.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

TODO: Replace the image below with your own.

Test\_score

![](RackMultipart20230121-1-5f87sc_html_4910a8e4d0eeaced.png)

## Summary

Steps:

- I obtained the data from the "Bike Sharing Demand" kaggle competition and opened the csv file via pandas library.
- Did data preprocessing and feature engineering; analyzed the data by using matplotlib library.
- Built the model using Autogluon. To start with, I built model without doing data preprocessing. Later, I added new features and did hyperparameter tuning.
- Sumbitted the csv file to my Kaggle profile.