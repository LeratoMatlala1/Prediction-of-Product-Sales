# Prediction of Product Sales

**Author:** Lerato Matlala

## Table of Contents

- [Project Overview](#overview)
- [Data](#data)
- [Method](#method)
  - [1. Exploratory and Explanatory Data Analysis](#1-exploratory-and-explanatory-data-analysis)
  - [2. Regression Model](#2-regression-model)
  - [3. Model Evaluation](#3-model-evaluation)
- [Conclusion](#conclusion)


## Project Overview

The primary objective of the Sales Prediction Project is to use regression models to provide precise and dependable predictions of sales. The main focus of this project is on regression models, specifically linear regression and random forest regression. This choice of models highlights the aim of developing predictive tools that can effectively analyze the complex connections between different factors, including product attributes, outlet characteristics, and historical sales data. By conducting thorough exploratory data analysis, our objective is to gain a comprehensive understanding of the complexity of the information, discern patterns and trends, and ensure the data is cleansed to facilitate trustworthy analysis. The project aims to enhance capabilities in accurately predicting sales patterns through the use of regression models.

## Data
The dataset used in this project contains information about items, outlets, and corresponding sales data. It consists of 8523 observations. The variables included in the dataset are as follows:


| Variable Name             | Description                                                  |
|---------------------------|--------------------------------------------------------------|
| Item_Identifier           | Unique identifier for each product                          |
| Item_Weight               | Weight of product                                           |
| Item_Fat_Content          | Product fat content type                                    |
| Item_Visibility           | Product visibility                                          |
| Item_Type                 | Product category                                            |
| Item_MRP                  | Maximum Retail Price                                        |
| Outlet_Identifier         | Store ID                                                    |
| Outlet_Establishment_Year | Store establishment year                                   |
| Outlet_Size               | Store size                                                  |
| Outlet_Location_Type      | Store location type                                         |
| Outlet_Type               | Store type                                                  |
| Item_Outlet_Sales         | Product sales (target variable)   

The objective is to build predictive models that accurately estimate sales based on these attributes.

## Method
### 1. Exploratory and Explanatory Data Analysis
The initial phase involves exploring the dataset to understand its structure, identify patterns, and detect any anomalies. EDA and ExDA help us visualize relationships between variables, discover trends, and prepare the data for modeling. This phase guides feature selection, and engineering, and prepares us for model construction.

#### Univariate Analysis
Univariate analysis involved exploring individual features. The analysis included histograms to visualize the distribution of numerical variables such as `Item_Weight` and `Item_MRP`. Boxplots were used to identify potential outliers in these variables. Count plots provided insights into categorical variables such as `Item_Fat_Content`, `Item_Type`, `Outlet_Size`, and `Outlet_Type`. 
Below is examples of some analysis that was done:

#### Multivariate Analysis
Multivariate analysis aimed to identify relationships between pairs of variables. A correlation heatmap was generated to visualize the correlations among numerical features. This helped in identifying potential collinearities and understanding variable interactions. Regression plots were also used to examine the relationship between numerical variables and the target variable `Item_Outlet_Sales`.

#### Feature Inspection
Feature inspection involved examining the features' distributions and characteristics. This step was crucial in identifying potential anomalies, patterns, and understanding the data's nature.

The types of analysis chosen were justified by their ability to provide a comprehensive understanding of the data's characteristics, distributions, and relationships. These insights guided feature engineering and selection for model development.


### 2. Regression Model

In the regression modeling phase, two primary regression models are considered: Linear Regression and Random Forest Regression. The Linear Regression model assumes linear relationships, while the Random Forest Regression can capture complex interactions between variables. Hyperparameter tuning is applied to the Random Forest model to optimize its performance and enhance its predictive capability.



