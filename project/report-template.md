# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### Barbara Cardoso

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
The first time without sapareting the date from hour the performance of the model was not so good, but improve with the data split. 

### What was the top ranked model that performed?
It was LightGBM_BAG_L1.

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
the exploratory analysis showed what a distribution was like according to the series, generating a hypothesis that with the categories and division of the datetime field, perhaps the execution of the model would be better. What happened to the season after, and to divide datetime into day, year and hour and it will transform as characteristics of the season. Furthermore, with hyperparameters it is possible to adapt and test different models to perform better.


### How much better did your model preform after adding additional features and why do you think that is?
It did improve the score because additional features can be good predictors to estimate the target value, in this case I decided to separate the date becuase it helps the model to analyse seasonality paterns in the data which can be usefull for a regression model.

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
Hyper parameter tuning with RF did improve model performance, comparing with NN model.

### If you were given more time with this dataset, where do you think you would spend more time?
Do a more extensive data analysis in order to get more information about this dataset, so this wey I could decide witch model and hiperparameters would result in a better trained model.

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model|hpo1|hpo2|hpo3|score|
|--|--|--|--|--|
|initial|default_vals|default_vals|default_vals|0.54023|
|add_features|default_vals|default_vals|default_vals|0.46916|
|hpo|regression|'GBM: num_boost_round: 100'|'FR:n_estimators: 300'|0.47809|

![Hyperparameter-table.png](img/Hyperparameter-table.PNG)
### Create a line plot showing the top model score for the three (or more) training runs during the project.


![model_train_score.png](img/model_train_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.



![model_test_score.png](img/model_test_score.png)

## Summary
In this project, the main objective is to predict bicycle demand from the library of historical bicycle data using an autogluon for various power models. At first I did all the necessary installation for executions, such as labs and connection to the kaggle API. The next step was to analyze the features in the training/test data for better performance. Then, the initial model was built with standard parameters and an exploratory analysis was carried out in relation to the model's performance.
The next steps are to do feature engineering to test the model again with the default pattern. After that, I tested differents hyperparameter and model for get the better model performing. At the end, an announcement of the final score was made in Kaggle and the final analysis was made by plotting the score and obtaining the best performance of the model.
