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

![alt text](https://github.com/Panasak/Thailand_House_Prices_Predictor/blob/main/data_clean/sactter_plot.png)
![alt text](https://github.com/Panasak/Thailand_House_Prices_Predictor/blob/main/data_clean/heat_plot.png)
![alt text](https://github.com/Panasak/Thailand_House_Prices_Predictor/blob/main/data_clean/box_plot.png)
![alt text](https://github.com/Panasak/Thailand_House_Prices_Predictor/blob/main/data_clean/bar_plot.png)
## Model Building
First I transformed the categorical variables into dummy variables. I also split the data into train and test sets with a test size of 33%
I tired three different models and evaluated them using Mean Absolute Error. I chose MAE because it is relatively easy to interpret and outliers aren't particularly bad in for this type of model.
I tried three different models:
* **Multiple Linear Regression** - Baseline for the model
* **Lasso Regression** - Because of the sparse data from the many categorical variables. I thought a normalized regression like lasso would be effective
* **Random Forest** - Again, with the sparsity associated with the data, I thought that this would be a good fit
## Model Performance
The Random Forest model outperformed the other approaches on the test and validation sets
* **Random Forest:** MAE = 4411561.95
* **Linear Regression:** MAE = 441239550501459.25
* **Lasso Regression:** MAE = 6423036.02
## Productization
In this step, I built a flask API endpoint that was hosted on a local webserver by following along with the TDS tutorial in the reference section above. The API endpoint takes in a request with a list of values for a house listing and return an estimated price.





