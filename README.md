# Insurance Linear Regression Project: Project Overview
This project uses linear regression to predict the insurance charges based on different attributes from age and sex to medical data.
* Create a tool that estamates insurance charges to help individuals estimates thier charges based on their physical attributes
* Engineered features to reduce the skewness using boxcox transformation technique
* Optimized Linear Regression using GridsearchCV to reach the best model
## Code and Resources Used
* **Python Version:** 3.7
* **Packages:** pandas, numpy, matplotlib, seaborn, sklearn, scipy
* **Kaggle Data:** https://www.kaggle.com/mirichoi0218/insurance

## About the Data
The data consists of the following columns:
* age
* sex
* bmi
* children
* smoker
* region
* charges
## Data Cleaning
First I removed outliers using Inter Quatile Range. Some of the rows were left skewed so I had to transform them using boxcox transformation in order to make the shape of the data more normal.

## EDA
I looked at the distributions of the data and the value counts for the various categorical variables. Below are a few highlights from the pivot tables.

![alt text](https://github.com/panasak/Insurance_Linear_regression/blob/main/overlap.png)
![alt text](https://github.com/panasak/Insurance_Linear_regression/blob/main/heat.png)
![alt text](https://github.com/panasak/Insurance_Linear_regression/blob/main/transform.png)

## Model Building
First I transformed the categorical variables into dummy variables. I also split the data into train and test sets with a test size of 33%
I scaled the data using StandardScaler from sklearn and used GridSearchCV for the parameter optimization of linear regression. 
I then created an instance of linear regression moddel using the optimized paramters and fit the data.
## Model Performance
I have choosen to use, MAE, MSE, RMSE, and Cooeficient of Determination to evaluate my model. The results are as follow:
* **MAE:** 0.41
* **MSE:** 0.43
* **RMSE:** 0.66
* **R^2:** 0.78
