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

In this project we use dat from CarDekho. Founded in 2008 it is India's leading online marketplace that helps individuals and dealers buy, sell, and manage their cars.
The data contains 8128 entries and 12 features correponding to car name, year bought, selling price, kilometers driven,fuel type,seller type, transmission type, owner type, mileage, engine in the units of cubic capacity (CC), max_power in the units of brake horsepower (bhp),torque and number of seats. We didn't use torque feature since the units used for different entries correspond to different physical quantities and some of them have fixed values while others show range of vlaues.
We then remove 215 rows with missing values for multiple columns, we are left with 7913 entries (2.6 % less statistics). 
We then remove 1.1% of these corresponding to "LPG" and "CNG" underrepresented gas fuel types and this leaves 7819 enries.
Then we remove duplicated rows, which drops entries to 6612 (removes 15 %).
We then remove 0.07% data corresponding to "Test Drive Car" of Owner category, and get 6607 entries.
After removing outliers (1.4 percent of remaining data) we are left with 6514 data points.



## Approach

Compare predictions of different Machine Learning models:
- Linear Regression
- Tree Methods
- Support Vector Machines





