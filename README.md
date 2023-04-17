![alt text](https://github.com/tw1107/Springboard-Capston-House-Price/blob/main/images/housesbanner.png)

# Ames House Price Prediction

Ask a home buyer to describe their dream house, and they probably won't begin with the height of the basement ceiling or the proximity to an east-west railroad. There are much more influences price negotiations than the number of bedrooms or a white-picket fence.

With 79 explanatory variables describing (almost) every aspect of residential homes in Ames, Iowa, the purpose of this project is to predict the final price of each home.

## 1. Problem Statement
How much are the residential homes in Ames, Iowa given all aspects/attributes of the properties?

## 2. Goal
1.	Build regression models to leverage attributes of properties to predict sales price.
2.	Provide useful house process prediction for setting data-driven budgets for buyers.
3.	Provide insightful tool for setting more reasonable prices when selling/buying properties.

## 3. Data
Ames House Dataset [Kaggle Dataset](https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques/data) with 79 attributes and sales prices of 1,460 properties. 
Features examples:
•	Exterior features: Exterior material quality, type of foundation, masonry veneer type
•	Interior features: heat condition, central air conditioning, kitchen quality
•	Location feature: Zoning classification, slope of property, physical location within city limits

## 4. Data Cleaning
[Data Cleaning Notebook](https://github.com/tw1107/Springboard-Capston-House-Price/blob/main/notebook/01_data_wrangling.ipynb)

Major steps:
1. Check for duplicates:  There are 0 duplicates for this dataset
2. Impute missing values
3. Transform numerical features to categorical when they are true catrgorical
4. Encode some categorical features as ordered numbers when there is information in the order

## 5. EDA
[EDA Notebook](https://github.com/tw1107/Springboard-Capston-House-Price/blob/main/notebook/02_EDA.ipynb)

**Sale Price** is what we are predicting, EDA is all related to SalePrice (our target feature). Below are some take away:

**Price of properties in Ames, Iowa** 
![alt text](https://github.com/tw1107/Springboard-Capston-House-Price/blob/main/images/Screenshot%202023-02-26%20at%201.53.12%20PM.png)

1. Average house sale price is around $180,000 in Ames.
2. There are a few properties over $500,000, but majority of houses are priced under $214,000.
3. The target variable is right skewed (positive skewness) and shows peakedness. As (linear) models fits better on normally distributed data, we require proper transformation. 

**The most important numeric predictors** 
![alt text](https://github.com/tw1107/Springboard-Capston-House-Price/blob/main/images/top10.png)

**Attributes most correlated with sale price** 
![alt text](https://github.com/tw1107/Springboard-Capston-House-Price/blob/main/images/Screenshot%202023-02-26%20at%202.12.07%20PM.png)

**Time vs Sale price** 
![alt text](https://github.com/tw1107/Springboard-Capston-House-Price/blob/main/images/year.png)

## 6. Feature Engineer & Modeling
[Feature engineering & ML Notebook](https://github.com/tw1107/Springboard-Capston-House-Price/blob/main/notebook/04_Modeling.ipynb)

**Feature Engineering Major Steps:**
1. Encode some categorical features as ordered numbers when there is information in the order
2. Create new features
3. Log transform of the skewed numerical features to lessen impact of outliers
4. Transformation of categorical features vis one-hot encoding
5. Split into testing and training datasets
6. Standardize the magnitude of numeric features using a scaler

**Modeling Major Steps:** 
Created below models with RandomizedSearchCV hyperparameter tuning for model optimization
1. Ridge 
2. Lasso 
3. ElasticNet
4. XGBoost
5. Gradient Boosting Regression
6. Light GBM
7. Stacking Model with ElasticNet as the meta_mode

Model Validation Metric:
1. RMSE
2. R Squared

![Model Performance Score](https://github.com/tw1107/Springboard-Capston-House-Price/blob/main/images/Screenshot%202023-02-26%20at%202.35.43%20PM.png)

## 7. Prediction Tool
The users can use the prediction tool (created by IPyWidget) to estimate the house price by adjusting the top 5 features. 
![Sale Price Prediction Tool](https://github.com/tw1107/Springboard-Capston-House-Price/blob/main/images/tool.png)

## 8. Future improvements
I would love to spend more time testing new hyperparameters or different modeling methods to predict the sale price even more accurately.








