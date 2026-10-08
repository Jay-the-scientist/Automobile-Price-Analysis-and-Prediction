# Automobile Price Prediction and Analysis

**Exploring the factors that influence automobile prices and using machine learning to estimate vehicle values.**

## Overview

What makes one automobile more expensive than another? Is it engine size, horsepower, fuel efficiency, or a combination of several characteristics?

This project explores these questions using historical automobile data. Through five Jupyter notebooks, I analyzed vehicle specifications, investigated relationships between automobile features and prices, and developed regression models to estimate vehicle values.

The project follows a complete introductory data science workflow, from preparing raw data to evaluating and refining prediction models.

## Dataset

The project uses the **Automobile dataset from the UCI Machine Learning Repository**, accessed through IBM's Data Analysis with Python coursework.

The original dataset contains **205 automobile records and 26 attributes**, including:

- **Price:** Automobile price, used as the prediction target
- **Engine size:** Engine displacement
- **Horsepower:** Engine power
- **Curb weight:** Vehicle weight
- **Highway MPG:** Highway fuel efficiency
- **Body style and drive wheels:** Vehicle design and drivetrain characteristics

**Source:** [UCI Automobile Dataset](https://archive.ics.uci.edu/dataset/10/automobile)

## Preparing the Data

Before analyzing automobile prices, I worked through several data preparation steps to make the dataset suitable for statistical analysis and machine learning.

These included:

- Identifying and handling missing values
- Correcting numerical data types
- Removing records without valid price information
- Normalizing selected numerical features
- Creating horsepower categories
- Encoding categorical variables for analysis

These transformations helped create a more consistent dataset for exploring relationships and developing regression models.

## Exploring Automobile Prices

### Engine Size and Price

One of the strongest relationships identified in the analysis was between engine size and automobile price.

![Engine Size vs. Automobile Price](images/5-enginesize-price-scatterplot.png)

The scatterplot shows a clear positive relationship: vehicles with larger engines generally had higher prices.

The correlation coefficient between engine size and price was approximately **0.872**, making engine size one of the strongest individual predictors examined.

### Fuel Efficiency and Price

I also explored the relationship between highway fuel efficiency and automobile price.

![Highway MPG vs. Automobile Price](images/7-highwaympg-price-scatterplot.png)

The analysis revealed a negative relationship between highway MPG and price, with a correlation coefficient of approximately **-0.705**.

Within this dataset, vehicles with higher highway fuel efficiency generally tended to have lower prices.

### Comparing Drive-Wheel Configurations

To examine how vehicle design relates to price, I compared average automobile prices across different drive-wheel configurations.

![Average Automobile Price by Drive-Wheel Configuration](images/17-averageprice-4wd-fwd-rwd.png)

Rear-wheel-drive vehicles had the highest average prices in this dataset, while front-wheel-drive and four-wheel-drive vehicles showed lower averages.

This comparison illustrates how categorical vehicle characteristics can be explored alongside numerical features.

## Identifying Important Price Factors

Correlation analysis helped identify which numerical vehicle characteristics were most closely associated with automobile price.

| Vehicle characteristic | Correlation with price |
|---|---:|
| Engine size | 0.872 |
| Curb weight | 0.834 |
| Horsepower | 0.810 |
| Vehicle width | 0.751 |
| Highway MPG | -0.705 |
| City MPG | -0.687 |

**Key takeaway:** Engine size, curb weight, and horsepower showed strong positive relationships with price, while fuel efficiency showed a negative relationship.

These relationships describe patterns in the historical dataset and do not establish that the features independently cause price changes.

## Building Price Prediction Models

After exploring the data, I developed several regression approaches to estimate automobile prices.

**Simple Linear Regression**

Used a single feature, such as highway MPG, to estimate automobile price.

**Multiple Linear Regression**

Combined horsepower, curb weight, engine size, and highway MPG to estimate price using multiple vehicle characteristics.

**Polynomial Regression**

Explored nonlinear relationships between automobile characteristics and price.

These approaches provided an opportunity to compare how different model structures represent the relationships observed in the data.

## Evaluating Model Performance

I evaluated the regression models using two metrics:

- **R² (Coefficient of Determination):** Measures how much variation in price is explained by the model.
- **Mean Squared Error (MSE):** Measures the average squared difference between predicted and actual prices.

### Actual vs. Predicted Prices

![Actual vs. Predicted Automobile Prices](images/36-actual-vs-predicted-values-distributionplot.png)

The distribution plot compares actual automobile prices with values estimated by the multiple linear regression model.

This visualization helps illustrate how closely the model's predictions follow the observed price distribution.

### Comparing Regression Models

![Automobile Regression Model Comparison](images/38-comparing-models.png)

The model development analysis reported the following results:

| Model | R² | MSE |
|---|---:|---:|
| Simple Linear Regression | 0.497 | 31.6 million |
| Multiple Linear Regression | 0.809 | 12.0 million |
| Polynomial Regression | 0.674 | 20.5 million |

Among these three approaches, **Multiple Linear Regression produced the strongest fit**, achieving the highest R² and lowest MSE.

These results come from the model development exercises and should not be interpreted as independent test-set performance.

## Model Refinement

The final notebook explored additional techniques for evaluating and improving regression models.

This included:

- Splitting the dataset into training and testing sets
- Comparing model performance on training and test data
- Examining overfitting and underfitting
- Exploring polynomial feature transformations
- Applying Ridge regression
- Using cross-validation and GridSearchCV for hyperparameter selection

These exercises demonstrate why model evaluation should consider performance on unseen data rather than relying only on training results.

## Technologies Used

- **Python** — Data analysis and model development
- **Pandas & NumPy** — Data preparation and numerical operations
- **Matplotlib & Seaborn** — Statistical visualization
- **SciPy** — Statistical analysis
- **scikit-learn** — Regression modeling, evaluation, and hyperparameter tuning
- **Jupyter Notebook** — Interactive analysis

## Skills Demonstrated

- Data cleaning and preprocessing
- Missing-value handling
- Feature engineering and encoding
- Exploratory data analysis
- Correlation analysis
- Data visualization
- Linear and polynomial regression
- Model evaluation using R² and MSE
- Training and testing workflows
- Regularization and hyperparameter tuning

## Project Context

This project was completed through the **IBM Data Analysis with Python coursework**.

The five notebooks document a guided, hands-on progression through data acquisition, preparation, exploratory analysis, model development, and model refinement.

The project demonstrates foundational data science and machine learning techniques rather than a production-ready automobile valuation system.
