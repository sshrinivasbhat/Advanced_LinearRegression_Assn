# Advanced Linear Regression Assignment

>
## Business Problem
	- A US-based housing company named Surprise Housing has decided to enter the Australian market. 
	- The company uses data analytics to purchase houses at a price below their actual values and flip them on at a higher price. 
	- For the same purpose, the company has collected a data set from the sale of houses in Australia. The data is provided in the CSV file below. 
	- The company is looking at prospective properties to buy to enter the market. 
	- You are required to build a regression model using regularization in order to predict the actual value of the prospective properties and decide whether to invest in them or not.
	- The company wants to know:
		- Which variables are significant in predicting the price of a house, and
		- How well those variables describe the price of a house. 

Also, determine the optimal value of lambda for ridge and lasso regression.
## Goal¶
	- Build a regression model using regularisation in order to predict the actual value of prospective properties and decide on investing.
	- Identify variables which are significant in predicting the price of the house
	- How well those variables describe the price of the house
	- Identify optimal value of ridge coefficients and lasso coefficients
	- Target : SalePrice
	- Predictors : 'OverallQual','OverallCond', 'MasVnrArea', 'BsmtFinSF1', 'BsmtFinSF2', 'BsmtUnfSF','TotalBsmtSF', '1stFlrSF', '2ndFlrSF', 'LowQualFinSF', 'GrLivArea' ....

## Table of Contents
* [General Info](#general-information)
* [Technologies Used](#technologies-used)
* [Conclusions](#conclusions)
* [Acknowledgements](#acknowledgements)

<!-- You can include any other section that is pertinent to your problem -->

## General Information
- Provide general information about your project here.
	Advanced Linear Regression Assignment - MLR for a bike sharing system.
- Background
	- A US-based housing company named Surprise Housing uses data analytics to purchase houses at a price below their actual values and flip them on at a higher price.
	- Data set has been collected from the sale of houses in Australia
	- data provided as train.csv
	- Identification of prospective properties to buy and enter the market
- Goal
	- Build a regression model using regularisation in order to predict the actual value of prospective properties and decide on investing.
	- Identify variables which are significant in predicting the price of the house
	- How well those variables describe the price of the house
	- Identify optimal value of ridge coefficients and lasso coefficients
	- Target : SalePrice
	- Predictors : 'OverallQual','OverallCond', 'MasVnrArea', 'BsmtFinSF1', 'BsmtFinSF2', 'BsmtUnfSF','TotalBsmtSF', '1stFlrSF', '2ndFlrSF', 'LowQualFinSF', 'GrLivArea' ....
- What is the dataset that is being used?
	- train.csv (description in data_description.txt)
- Python Notebook
	- C44UG_HousePricePred_ShrinivasB.ipYnb
- Document	
	- C44UG_HousePricePred_ShrinivasB.pdf
<!-- You don't have to answer all the questions - just the ones relevant to your project. -->

## Conclusions
### Multiple Model options were tried with various configurations for Linear,Ridge and Lasso Regression
     - Model Variations
	- Model-1 Min-Max Scaling for Target and Predictor Variables,Log Transformation for Target Variable
	- Model-2 Min Max scalinhg for Target and Predictor Variables,Log Transformation for Target Variable,Doubling of Optimal Regularization parameters obtained for Lasso and Ridge
	- Model-3 Min-Max Scaling applied for Predictor Variables only,Log transformation of Target Variable
	- Model-4 Min-Max Scaling applied for Predictor Variables,No Transformation of Target Variable
	- Model-5 Min-Max Scaling applied for Predictor Variables+ Target Variable , No Transformation of Target Variable
	- Lasso Regression was also tried with elimination of the top-5 predictors for each Model
	- In some of the models the log transformationm on the target variable was perfomed as the target variable showed some skewness in its distribution	
	- Results considering Model-1
		- GrLivArea,Condition2_PosN,Condition2_PosA,OverallQual_8,OverallQual_9 are the top predictors with Lasso Regression
		- After Eliminating this variables new variables obtained from the Lasso Model are YearBuilt_1893, 1stFlrSF, 2ndFlrSF, OverallQual_10, OverallQual_3
		- GrLivArea,GarageArea,1stFlrSF,OverallQual_9,BsmntFinSF1 are the top-5 Predictors for Ridge Regression
		- Optimal Regularization alpha is 7 for ridge and 1e-04 for Lasso Regressions
		- Ridge seems to be a Marginaly better in terms of generalization as difference in R2_Score,Residual-erros between test and training data
		- Lasso regression also gives higher RMSE with test data
		- Marginal RMSE degradation with Lasso regression when top-5 predictor variables eliminated.(Compared to Lasso with those predictor variables)
	- Across Models Inferences
		- 3-4 Predictors among the Top-5 Predictors found to be mostly same across all the Model Variations for Lasso Regression. (GrLivArea, GarageArea, OverallQual_8, OverallQual_9)
		- 3-4 Predictors among the Top-5 Predictors found to be mostly same across all the Model Variations for Ridge Regression (GrLivArea,1stFlrSF, OverallQual_8, OverallQual_9)
		- 3 Predictors among the Top-5 Predictors are mostly same between Ridge and Lasso Regression for most of the Models.
		- Top predictor variables with and without Min-Max scaling of the Target variable is same. (Model-4 and Model-5)

## Technologies Used
	- python - version 3.9.x
	- numpy - version  1.21.5
	- pandas - version 1.4.2
	- seaborn - version 0.11.2
	- sklearn - version 1.0.2
	- statsmodels - version 0.13.2
	- scipy- version 1.7.3
	- matplotlib- version 3.5.1

import warnings
warnings.filterwarnings('ignore')

<!-- As the libraries versions keep on changing, it is recommended to mention the version of library used in this project -->

## Acknowledgements
Give credit here.
- This project executed is an graded assignment from upgrad
- References - upgrad-course material , upgrad documents.



## Contact
Created by Shrinivas Bhat [@sshrinivasbhat] - feel free to contact me!


<!-- Optional -->
<!-- ## License -->
<!-- This project is open source and available under the [... License](). -->

<!-- You don't have to include all sections - just the one's relevant to your project -->
