# Data-Cleaning-in-Python

## Introduction
This report presents the analysis and modelling of a dataset for a regression task.  The goal is to build a linear regression model to predict a target variable based on a set of features The report provides an overview of the dataset, exploratory data analysis, feature selection methods, linear regression models with different feature sets, and an analysis of the results.
## Dataset Analysis
Initially, our dataset had 1889 rows and 18 columns. We dropped unrequired columns that I didn’t find suitable. Later on, we performed univariate and multivariate analysis to observe the relationships between different several features The final dataframe used for modeling has a shape of (N, M), where N represents the number of samples and M represents the number of selected features.

## EDA
# Univariate Analysis
   
![image](https://github.com/SurinderSurme/Data-Cleaning-in-Python/assets/103140222/a62b988f-bcd5-4555-a10f-4af675306d78)

 ![image](https://github.com/SurinderSurme/Data-Cleaning-in-Python/assets/103140222/8e755ff6-dbf7-4b15-8ea0-2831f5fdafb5)

![image](https://github.com/SurinderSurme/Data-Cleaning-in-Python/assets/103140222/55c90cb4-b169-4860-9750-6f9714f24a98)

We performed univariate analysis on some of the features. Here, we can observed that most of Most of the Number of  rating are at the range of  0 - 30. Number of ratings where high around 15  and the density value was between 0.08-0.10.

## Multivariate Analysis
We observed a relationship between cbrt_NumberRatings and cbrt_Student Both are directly propotional to each other. As the Number Ratings increase the demand of student also increase .
  ![image](https://github.com/SurinderSurme/Data-Cleaning-in-Python/assets/103140222/c80576c0-faa8-423f-be2a-a7de37a92395)
 ![image](https://github.com/SurinderSurme/Data-Cleaning-in-Python/assets/103140222/bca44345-49e4-4761-bcbf-2541bfbb59b3)


From the second plot, we can see that as Number Ratings increase Enrollment increases.

## .Feature Observation and hypothesis

To find the most pertinent characteristics for the regression models, four feature selection strategies are used.
## Correlation -Based Selection:
subset of characteristics is manually chosen in accordance with their association with the target variable using the correlation matrix as a guide. Included in this list are the characteristics "NumberRatings," "cbrt_Enrollment," "Enrollment," "cbrt_Student," "InstRating," "Student," "Fee," and "Duration."
![image](https://github.com/SurinderSurme/Data-Cleaning-in-Python/assets/103140222/2ac206be-000b-40bb-89df-d81c70a86003)

 
## Variance Threshold Selection:
Variance threshold selection is used to assess the characteristics. Columns that are not numeric are removed, and a variance threshold of 2.5 is used. The chosen features are included in the final DataFrame, df_vt.
![image](https://github.com/SurinderSurme/Data-Cleaning-in-Python/assets/103140222/145755d5-11eb-4b5c-9759-c70b268fe0d9)

 

## SelectKBest Method :  
best K features are selected using the SelectKBest technique, which is based on univariate statistical tests. The train_test_split() method divides the feature sets into training and testing sets, and the f_regression score function creates the SelectKBest instance. The extracted characteristics are put in a DataFrame called df_selKBest after being extracted.

![image](https://github.com/SurinderSurme/Data-Cleaning-in-Python/assets/103140222/f83f68b6-9219-48e9-b90e-87a2def1d9b0)


 ## Simple Linear Regression Report
In this section, several feature selection techniques were used to build linear regression models. The following strategies for feature selection were used:
Selection based on correlation: The characteristics having the highest absolute correlation values with the cbrt_NumberRatings target variable were chosen. 'NumberRatings', 'cbrt_Enrollment', 'Enrollment', 'cbrt_Student', 'InstRating', 'Student', 'Fee', and 'Duration' were the features that were chosen.Variance Features having a variance greater than a threshold value (2.5) were chosen. ChooseKBest approach: Based on the F-regression score, the top 7 characteristics were chosen.We trained linear regression models for each feature selection technique. The R2 score and root mean squared error (RMSE) were used to assess each model's performance. There was also a display of the coefficients for the chosen characteristics.
## Linear Regression with Lasso Report: 
Lasso regression was applied to the dataset using different alpha values. The performance of the models was evaluated using the R2 score and RMSE. The best alpha value was selected based on the highest R2 score and lowest RMSE.
![image](https://github.com/SurinderSurme/Data-Cleaning-in-Python/assets/103140222/907b8973-b49c-4ff8-a92c-440e5ae02702)

 
## Analysis
Below is a table summarising the outcomes of several feature engineering techniques and the corresponding performance metrics:
 ![image](https://github.com/SurinderSurme/Data-Cleaning-in-Python/assets/103140222/05cdd39f-e24b-43c5-b5cb-35daac91bac3)



The SelectKBest approach earned the greatest R2 score and lowest RMSE value, which indicates higher performance when compared to other methods, as can be seen in the table.



