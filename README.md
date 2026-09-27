# 🏙️ NYC Airbnb Review Activity Prediction

## Overview

This project explores the factors associated with **Airbnb listing review activity in New York City** using exploratory data analysis and machine learning.

The primary objective is to build regression models that predict `reviews_per_month`, which is used as a proxy for **listing popularity and review activity**. The analysis uses listing characteristics such as price, minimum stay requirements, room type, location, availability, previous review activity, and host information.

The project follows an end-to-end machine learning workflow, including data exploration, preprocessing, feature engineering, model development, hyperparameter tuning, and performance evaluation.

## Dataset

The project uses the **NYC Airbnb Open Data** dataset, containing **48,895 Airbnb listings** across New York City and 16 features.

The dataset includes information about:

- Listing price
- Minimum number of nights
- Room type
- Neighbourhood and borough
- Geographic coordinates
- Number of reviews
- Review activity
- Last review date
- Host information
- Listing availability

Because `reviews_per_month` is the prediction target, listings without a recorded value for this variable were removed before modeling. This resulted in **38,843 listings** available for analysis.

## Project Objective

The primary prediction problem is:

> **Can we predict an Airbnb listing's monthly review activity based on its listing, host, pricing, location, and availability characteristics?**

`reviews_per_month` is used as a proxy for listing popularity because the dataset does not provide a direct popularity measure.

The project aims to:

- Explore patterns in Airbnb listing and review activity
- Identify relationships between listing characteristics and monthly review activity
- Clean and preprocess numerical and categorical features
- Engineer features that may improve predictive performance
- Compare multiple regression algorithms
- Tune model hyperparameters
- Evaluate and compare model performance using appropriate regression metrics

## Methodology

### 1. Exploratory Data Analysis

The analysis begins by examining the distribution and characteristics of the Airbnb listings.

Key observations include:

- Manhattan and Brooklyn contain the largest number of listings
- `price` is strongly right-skewed, with a small number of high-price outliers
- Listing location is closely related to latitude, longitude, and neighbourhood
- `reviews_per_month` contains missing values for a substantial portion of the original dataset
- Review activity varies considerably across listings

### 2. Data Preprocessing

The dataset is split into training and testing sets using a **70/30 split** with a fixed random state for reproducibility.

Missing values and categorical variables are handled through preprocessing pipelines before being passed to the regression models.

### 3. Feature Engineering

Additional features are created to represent characteristics that may be relevant to listing activity.

For example:

```python
minimum_stay_price = price × minimum_nights
```

This feature represents the minimum potential cost of a stay based on the listing's nightly price and minimum-night requirement.

Other available listing characteristics, including location, room type, review history, availability, and host information, are also considered as predictive features.

### 4. Regression Models

Multiple regression approaches are compared as part of the modeling workflow.

The project includes:

- Baseline regression
- Linear/Ridge regression
- Tree-based regression
- Random Forest regression
- Hyperparameter optimization

Models are evaluated on held-out test data to compare their predictive performance.

## Technologies Used

- **Python**
- **Pandas**
- **NumPy**
- **Matplotlib**
- **Seaborn**
- **Scikit-learn**
- **Jupyter Notebook**

## Key Skills Demonstrated

- Exploratory Data Analysis (EDA)
- Data Cleaning
- Feature Engineering
- Regression Modeling
- Machine Learning Pipelines
- Categorical Feature Encoding
- Missing Value Handling
- Model Evaluation
- Hyperparameter Optimization
- Data Visualization
- Reproducible Machine Learning

## Results

The project evaluates multiple regression models for predicting `reviews_per_month` and compares their performance after preprocessing, feature engineering, and hyperparameter tuning.

The final notebook documents the modeling process, evaluation metrics, and performance differences between the approaches.

### Key Findings

Add a few concrete findings from the completed analysis here. For example:

- Which listing characteristics showed the strongest relationship with review activity
- How pricing and minimum stay requirements related to predicted review activity
- How model performance changed after feature engineering
- Which regression approach achieved the strongest test performance
- Important limitations of using `reviews_per_month` as a proxy for listing popularity

## Project Structure

```text
nyc-airbnb-price-analysis/
│
├── nyc_airbnb_price_analysis.ipynb
├── README.md
└── LICENSE
```

## Notes and Limitations

`reviews_per_month` should be interpreted as a measure of **observed review activity**, rather than a direct measure of bookings or overall Airbnb popularity.

A review is not necessarily generated for every booking, so the target variable has limitations as a proxy for listing demand.

Additionally, the dataset represents Airbnb listings from **New York City** and therefore the findings should not automatically be generalized to other cities or time periods.

## Project Focus

**Data Analysis · Machine Learning · Regression · Feature Engineering · Airbnb Review Activity**
