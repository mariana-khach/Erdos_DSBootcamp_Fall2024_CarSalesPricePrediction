# mariana-khach

This repository contains files for a project I proposed during my participation in Fall 2024 Erdos Data Scinece Bootcamp.
In this project we use car sales data from CarDekho.com, which is an online marketplace that helps people buy and sell cars in India.
We use different car features to predict sales price.
There are four other Erdos bootcamp members that work on this project in the same group with me. 
While this repository contains my analysis,
the analysis of all group members can be found in the following collaborative github repository https://github.com/parabamoghv/Erdos-AU2024-CarSalesPricePrediction



# Modeling the relationship between car sales price and different car features

Buying and selling cars is common experience especially among people leaving in rural areas with little or no transportation.
It is thus interesting to study what factors do influence car sales price significantly and what can be improved to have better sales and fair car sales prices.
Using differnt Machine Learning Regression methods we will develop models to predict car sales price using [CarDekho Dataset](https://www.kaggle.com/datasets/nehalbirla/vehicle-dataset-from-cardekho/data?select=Car+details+v3.csv) .

## Authors

- [Mariana Khachatryan](https://github.com/mariana-khach)
- [Adreja Mondol](https://github.com/adrejamondol)
- [Amogh Parab](https://github.com/parabamoghv)
- [Nasim Dehghan](https://github.com/nasimdeh)


## KPI

#### Technical performance Key Performance Indicators (KPIs)

1.	Mean Absolute Error (MAE)
2.	Mean Squared Error (MSE)
3.	Root Mean Squared Error (RMSE)
4.	R-squared- proportion of variance in target variable that is predictable from input features

#### Business impact KPIs

These KPIs measure how effectively the model adds value to the business, such as improving pricing strategies or increasing customer satisfaction.
1.	Revenue Increase: Accurate price predictions could help optimize the selling price of cars, leading to better margins.
2.	Cost Reduction: If the model is used to automate pricing, it can reduce the need for manual evaluation and pricing, saving labor costs.
3.	Inventory Turnover Rate: How quickly cars are being sold after their prices are set by the model.

## Key Stakeholders

1.	Car Dealerships need price prediction model to set competitive and accurate prices for cars. Dealerships want to maximize profit while ensuring quick car sales. Accurate price prediction results in competitive pricing and profitability.
2.	Customers can use the model to estimate whether the set price is fare.



## Exploratory Data Analysis and Feature Engineering

In this project we use data from CarDekho. Founded in 2008, it is India's leading online marketplace that helps individuals and dealers buy, sell, and manage their cars.
The data contains 8128 entries and 12 features corresponding to car name, year bought, selling price, kilometers driven, fuel type, seller type, transmission type, owner type, mileage, engine in the units of cubic capacity (CC), max_power in the units of brake horsepower (bhp), torque and number of seats. We didn't use torque feature since the units used for different entries correspond to different physical quantities and some of them have fixed values while others show range of values. We also dropped car name feature, since it had too many unique categories.
- Data cleaning involved:
  - removal of duplicated rows, which dropped entries to 6926 (removed 14.79% of data)
  - removal of 209 rows with missing values for multiple columns, which reduced entries to 6717 (3.02% less statistics)
  - removal of 1.28% of remaining data corresponding to "LPG" and "CNG" underrepresented gas fuel types which left 6631 entries
  - removal of 0.08% data corresponding to "Test Drive Car" of owner category which left 6626 entries
  - removal of outliers (5.42% of remaining data) 
- Final data set had 6533 data points with 9 features 
- Feature engineering
  - we modified number of seats feature to have two bins for number of seats >5 and seats<=5
    ![Nseats](https://github.com/user-attachments/assets/cdad7d03-64a4-4c7b-9972-2c52f4d147f7)
  - we combined "Trustmark Dealer" with "Dealer" categories in seller type feature, to decrease imbalance between different categories
    ![dealer](https://github.com/user-attachments/assets/5c4fc41a-5d9e-4938-99bf-83f3be569d2a)
    
We then used one hot encoding for categorical features (fuel type, seller type, transmission type, owner type, number of seats bin category).
- Exploratary data analysis:
  - we have looked at the correlation of sales price with different feature
    ![salesprice_corr](https://github.com/user-attachments/assets/0a7ef427-fb65-4007-8880-aa1d838f95f8)
  - sales price has highest correlation with max power
    ![salesprice_maxpower](https://github.com/user-attachments/assets/56d2330a-7fff-4608-9568-8eba2f533b17)
  - Before model training, correlated features were removed, i.e. only one feature among features with correlation > 0.8 was kept.
    ![2D_corr](https://github.com/user-attachments/assets/708235f7-1d9a-4bb5-bf5b-d44f5c26655a)

We can see the distributions of sales price for differnt categorical features in the violin plots below. the distributions look different for different categories of given categorical feature, which suggests that they should all be included in training of model.
![price_fuel](https://github.com/user-attachments/assets/fa84906e-8be6-43e2-8f2e-0108747e7b26)
![price_sellertype](https://github.com/user-attachments/assets/5daee49e-c9b9-4240-bb7b-5302d84650f5)
![price_transmission](https://github.com/user-attachments/assets/122ebd1a-0053-402b-89ff-6fc17216dd83)
![price_Nseats](https://github.com/user-attachments/assets/14c60686-74af-4156-872e-69eb2db58c56)
![price_owner](https://github.com/user-attachments/assets/94adbec0-f007-41a0-91f8-ebd918d129c2)


## Approach

We compare predictions of different Machine Learning models:
- Linear Regression
- Tree Methods
- Support Vector Machines
We start with linear regression models, such as Elastic Net from python sklearn library. Elastic Net uses combination of Lasso and Ridge regularizations. We will then compare results from different regression models. We use grid search to find optimal model parameters for different regression methods. 





