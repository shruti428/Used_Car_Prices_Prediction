# Used Car Price Analysis

This project analyzes used vehicle listing data to identify the key drivers of used car prices and develop predictive machine learning models that support data-driven pricing and inventory decisions for used car dealers.

The analysis explores how factors such as vehicle model, manufacturer, condition, mileage, title status, and fuel type influence vehicle prices.

---

# Data & Methodology

| Attribute | Details |
|---|---|
| Problem Type | Supervised Regression |
| Objective | Predict used car prices |
| Dataset | Used vehicle listings dataset |
| Features | Manufacturer, model, year, odometer, condition, fuel type, transmission, title status, location, vehicle type |
| Feature Engineering | Car age and preprocessing of categorical variables |
| Models Used | Linear Regression, Ridge Regression |
| Evaluation Metrics | RMSE and R² |

---

# Exploratory Data Analysis (EDA)

## Insights from Continuous Variables

### Price
- Right-skewed distribution
- Most vehicles priced below \$40,000

### Year
- Left-skewed distribution
- Majority of vehicles manufactured after 2000

### Odometer
- Right-skewed distribution
- Most vehicles have mileage under 200,000

---

## Insights from Categorical Variables

### Manufacturers
- Ford and Chevrolet are the most common manufacturers with over 50,000 vehicles listed

### Vehicle Models
- F-150 and Silverado are the most frequently occurring models

### Condition
- Majority of vehicles are listed in good or excellent condition

### Fuel Type
- Most vehicles run on gas

### Transmission
- Automatic transmission is the most common

### Title Status
- Most vehicles have clean titles

### Vehicle Type
- SUVs and sedans are the most common vehicle types, followed by pickup trucks

---

# Relationship Between Price and Features

- Weak linear correlation exists between price and year/odometer
- Significant price variation exists across:
  - Manufacturer
  - Model
  - Condition
  - Title status
- Vehicles with clean titles and better condition generally have higher prices
- Diesel and electric vehicles tend to have slightly higher prices
- Salvage or missing-title vehicles have significantly lower prices

---

# Model Performance

| Model | R² | Insight |
|---|---|---|
| Linear Regression (Log Price - All Features) | ~0.43 | Strong baseline |
| Linear Regression (Log Price - Drop Model Feature) | ~0.34 | Significant performance drop |
| Ridge Regression (Log Price) | ~0.44 | Slight improvement |
| Ridge Regression (Raw Price) | ~0.49 | Best performing model |

## Key Findings

- The Ridge Regression model using raw prices provided the best explanatory performance
- Log transformation improved model stability by reducing skewness but did not outperform the raw-price Ridge model
- The raw-price Ridge model is recommended because of:
  - Better explanatory power
  - Easier business interpretability
- Log-transformed models may still be useful for handling outliers
- Removing the vehicle model feature significantly reduced performance, highlighting its importance

---

# Key Drivers of Vehicle Price

## Vehicle Model
- Strongest predictor of vehicle price
- High-end models significantly increase price

## Manufacturer
- Luxury brands are associated with higher prices
- Economy brands are associated with lower prices

## Condition & Title Status
- Better condition and clean titles increase value
- Salvage or missing titles reduce price significantly

## Car Age
- Limited incremental impact when model information is included
- Non-linear transformations did not improve model performance

---

# Business Recommendations

## Inventory Strategy
- Focus on high-value brands and popular vehicle models
- Prioritize vehicles in excellent condition with clean titles

## Pricing Strategy
- Vehicle model and manufacturer should drive pricing decisions
- Adjust prices based on:
  - Condition
  - Mileage
  - Title status

## Data Strategy
- Improve data quality, especially for vehicle model information
- Capture additional features such as:
  - Vehicle trim
  - Features/options
  - Market demand indicators

---

# Conclusion

Vehicle model, manufacturer, and condition are the most influential factors affecting used car prices. The final Ridge Regression model explains approximately 49% of price variation. Further improvements in data quality and feature engineering could enhance predictive performance and business value.

---

# Repository Contents

```text
├── Used_Car_Price_Analysis.ipynb     # Jupyter notebook with full analysis
├── data/
│   └── vehicles.csv.zip                  # Raw dataset
└── README.md                         # Project overview
```

---

# About

This project applies exploratory data analysis and machine learning techniques to understand the major factors influencing used car prices and provide actionable insights for used car dealers.

---

# Languages Used

- Python
- Jupyter Notebook
- Pandas
- Scikit-learn
- Matplotlib
- Seaborn
