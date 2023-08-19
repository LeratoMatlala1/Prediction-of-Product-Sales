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
- [Recommendations](#recommendations)
- [Limitations](#limitations)


## Project Overview

The primary objective of the Sales Prediction Project is to use regression models to provide precise and dependable predictions of sales. The main focus of this project is on regression models, specifically linear regression and random forest regression. This choice of models highlights the aim of developing predictive tools that can effectively analyze the complex connections between different factors, including product attributes, outlet characteristics, and historical sales data. By conducting thorough exploratory data analysis, our objective is to gain a comprehensive understanding of the complexity of the information, discern patterns and trends, and ensure the data is cleansed to facilitate trustworthy analysis. The project aims to enhance capabilities in accurately predicting sales patterns through the use of regression models.

## Data
The dataset used in this project contains information about items, outlets, and corresponding sales data. It consists of 8523 observations and 12 Features. The variables included in the dataset are as follows:


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

Below are examples of some univariate analysis that was done:

![download](https://github.com/LeratoMatlala1/Prediction-of-Product-Sales/assets/138568742/b3491d54-8fbb-4240-9dd1-3a9731b327d3)
-----------------------
![Boxplots of Numerical Features](https://github.com/LeratoMatlala1/Prediction-of-Product-Sales/assets/138568742/b76f0f54-b3a0-41d0-b4c9-629dff4797dc)
-------------------
![Coutplots of Categorical Features](https://github.com/LeratoMatlala1/Prediction-of-Product-Sales/assets/138568742/8f6579c3-e7b3-4c59-b402-50798b54eda9)
-------------------

#### Multivariate Analysis
Multivariate analysis aimed to identify relationships between pairs of variables. A correlation heatmap was generated to visualize the correlations among numerical features. This helped in identifying potential collinearities and understanding variable interactions. Regression plots were also used to examine the relationship between numerical variables and the target variable `Item_Outlet_Sales`.

Below is an example of some multivariate analysis that was done:

![download (1)](https://github.com/LeratoMatlala1/Prediction-of-Product-Sales/assets/138568742/a1c01b96-293d-44a8-b6f6-bc40a0806b9e)
-------------------
![Regression Plots](https://github.com/LeratoMatlala1/Prediction-of-Product-Sales/assets/138568742/026ee035-fc90-4213-a10b-a219b44d8975)
---------------

#### Feature Inspection
Feature inspection involved examining the features' distributions and characteristics. This step was crucial in identifying potential anomalies, patterns, and understanding the data's nature.

The types of analysis chosen were justified by their ability to provide a comprehensive understanding of the data's characteristics, distributions, and relationships. These insights guided feature engineering and selection for model development.


### 2. Regression Model

In the regression modeling phase, two primary regression models are considered: Linear Regression and Random Forest Regression. The Linear Regression model assumes linear relationships, while the Random Forest Regression can capture complex interactions between variables. Hyperparameter tuning is applied to the Random Forest model to optimize its performance and enhance its predictive capability.

### 3. Model Evaluation

The performance of the developed models is rigorously evaluated using various metrics, including R-squared, Mean Absolute Error (MAE), Mean Squared Error (MSE), and Root Mean Squared Error (RMSE). These metrics provide insights into the accuracy of the models' predictions and their ability to generalize to new data. Comparisons between training and test data shed light on potential overfitting or underfitting issues.

Here are the key metrics for the three models:

| Model                    | R-squared   | MAE       | MSE         | RMSE      |
|--------------------------|-------------|-----------|-------------|-----------|
| Linear Regression        | 0.561       | 847.325   | 1300023.710 | 1140.186  |
| Default Random Forest    | 0.540       | 781.355   | 1269309.504 | 1126.636  |
| Tuned Random Forest      | 0.603       | 728.453   | 1096307.534 | 1047.047  |

#### Key Insights
- The Tuned Random Forest model outperforms both the Linear Regression and Default Random Forest models in all metrics.
- The Tuned Random Forest model's R-squared value of 0.603 suggests it can explain around 60.3% of the variability in sales.
- The lower MAE, MSE, and RMSE values of the Tuned Random Forest model indicate its predictions are closer to actual sales values.
- The Tuned Random Forest model offers a promising solution for accurate sales prediction, beneficial for business decisions.

## Conclusion

The final model chosen for deployment is the tuned Random Forest Regression model. After hyperparameter tuning, this model demonstrated improved performance on both training and test data compared to the default Random Forest and Linear Regression models. The tuned model strikes a balance between capturing complex relationships and avoiding overfitting.

The primary business problem is predicting sales accurately to support decision-making and resource allocation. The metrics collectively indicate that the tuned Random Forest Regression model is capable of providing reasonably accurate sales predictions, which can assist businesses in making informed decisions.

## Recommendations

Based on the analysis and model performance, the following recommendations can be made:

- **Utilize the Tuned Random Forest Model:** The tuned Random Forest model has demonstrated superior predictive performance compared to other models. It is recommended for accurate sales predictions and informed decision-making.

- **Continuous Data Collection:** Collect and incorporate more recent sales data to further enhance the model's predictive capabilities and adapt to changing sales trends.
  
- **Feature Engineering:** Explore advanced feature engineering techniques to capture more nuanced relationships between features and sales.
- **Ensemble Methods:** Experiment with ensemble methods like stacking and boosting to further enhance model performance.

  
## Limitations

Despite the success of the models, there are certain limitations:

- **Feature Availability:** Some features, such as item demand trends or external economic factors, might not have been included in the dataset. Incorporating these features could potentially improve prediction accuracy.

- **Assumption of Stationarity:** The models assume that sales patterns remain consistent over time. If significant shifts in consumer behavior occur, the models may need recalibration.
