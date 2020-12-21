# Syntactic-Minority-Oversampling-Techniques-and-Regression

1) Replaced the “Top10perc” variable with a factor variable “Elite” with two levels: “Yes” if 50% or more of new students coming from the top 10% of their high school class (that is, if Top10Perc>=50) , and “No” if less than 50% of new students are coming from the top10% of their high school class.

2) Normalized all numerical features (except the “Apps” variable) using z-score standardization using “scale” function.

3) Used caret package to run 10 fold cross validation using linear regression method on all features.  Printed the resulting model to see the cross validation RMSE. In addition, took a summary of the model and interpreted the coefficients.

4) Used caret and leap packages to run a 10 fold cross validation using step wise linear regression method with backward selection (i.e., method=”leapBackward). The train method by default uses maximum of 4 predictors and reports the best models with 1..4 predictors. Changed this parameter to consider 1..16 predictors. Inside the train function, added the following parameter tuneGrid = data.frame(nvmax = 1:16). Took the summary of the final model to see which variables were selected in the model with the lowest RMSE.

5) Split the data into train and test (Used the first 621 rows for training and rest for testing). Used “rpart” function to create a regression tree model from the training data. Got predictions on testing data and computed the RMSE.

#Predicting Loan Defaults

6) Trained a logistic regression model on the train data using the glm package and used it to predict default for test data.

7) Compared the predictions with the actual default labels in the test data. Determined false positive rate and false negative rate of the model.

8) Used SMOTE (Syntactic Minority Oversampling Technique) which uses KNN to generate syntactic samples for the minority class. Installed the DMwR package in R and use the SMOTE function to generate syntactic training data for the minority class. 

9) Used perc.over=100 argument in the SMOTE function and left other parameters as default to create a balanced training data. 

Trained a logistic regression model on this balanced data and evaluated it on test data. 

Compared the False Positive & False Negative Rates of the model trained on balanced data to the previous model trained on imbalanced data and discussed
their differences.
