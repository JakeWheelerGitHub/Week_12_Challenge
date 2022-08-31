# Module 12 Report Template

## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

* The purpose of this analysis is the create a model that can predict healthy loans and high-risk loans. This is done by creating a logistic regression model. The model will look at several financial factors to learn if the loan will be classified as healthy or risky. The model will then analyze data that it didn't learn from and predict whether that loan is risky or healthy. The predicted value will then be compared to the actual value to see how the model performs. Two versions of this model will be created with intent to determine the best model version. The difference between the two models will be how the data given to them is processesed and will be discussed in detail below.
* The financial factors the model is looking at are loan size, interest rate,	borrower income, debt to income, number of accounts, derogatory marks, and total debt. The only factor it will be predicting is the loan classification into one of two categories: healthy or high-risk.
* The reason that two versions of the model will be tested is because of the uneven amount of healthy to high-risk loans. In the data set analyzed there are 75036 healthy loans and only 2500 high-risk loans. This was determined using the value_counts function. This discrepency can impact how the model learns since it overwhelmingly learns on healthy loans. One version of the model will analyze the data set as it exists. The second version of the model will analyze the data set once the data has been processed by oversampling. This changed the dataset to have equal values of 56271 healthy and high-risk loans for the model to learn on. 
* The model was through several steps. First that data set was split into training/testing data and split into labels/features. A logistic regression model was then created and fit to the original data. Once the model was fit, loan status predictions were made using this model. The models accuracy and classification report were printed. This process was then repeated for the second model, but only after the training dataset was oversampled. 
* `LogisticRegression` was used to create the model. `RandomOversampler` was used to oversample the data.

## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:
  * Description of Model 1 Accuracy, Precision, and Recall scores.
  The model has an accuracy of 0.9520479254722232. The accuracy is the measure of the correct predictions to total predictions.
  The model has a precision of 1.00 for the healthy loans and 0.85 for high-risk loans. The precision is the percect of positive predictions that are correct or the ratio of true positive predictions to all positive predictions. 
  The model has an recall of 0.99 for the healthy loans and 0.91 for high-risk loans. Recall is the percent of positive instances identified compared to all positive instances.



* Machine Learning Model 2:
  * Description of Model 2 Accuracy, Precision, and Recall scores.
  The model has an accuracy of 0.9936781215845847. 
  The model has a precision of 1.00 for the healthy loans and 0.84 for high-risk loans. 
  The model has an recall of 0.99 for the healthy loans and 0.99 for high-risk loans.
## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
* Which one seems to perform best? How do you know it performs best?
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )
  
  The model created with oversampling seems to perform better. Only three values were different between the two models: accuracy, 0 precision, and 0 recall. The model with oversampling has a higher accuracy (.99 compared to .95), a higher 0 recall (.99 compared to .91), and a 0.1 lower 0 precision (.84 compared to .85). The model with oversampling has an improved accuracy and recall with only a very slightly worse precision. This is not suprising considering the data was oversampled to provide more instances of 0 values. Now the model is more accurate at predicting 0 values (recall), but also has a higher frequency of false positives (lowering the precision). The most important aspect of the model is the ability to catch high-risk loans (predict the 0's). Because the model with oversampling is more capable of this (higher 0 recall score) the model is more suitable for our needs.


If you do not recommend any of the models, please justify your reasoning.
