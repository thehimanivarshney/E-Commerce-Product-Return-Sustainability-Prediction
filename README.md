E-Commerce-Product-Return-Sustainability-Prediction

**Author:** Himani Varshney

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Machine_Learning-orange.svg)](https://scikit-learn.org/)
[![XGBoost](https://img.shields.io/badge/XGBoost-Optimized-green.svg)](https://xgboost.readthedocs.io/)
[![Pandas](https://img.shields.io/badge/Pandas-Data_Analysis-150458.svg)](https://pandas.pydata.org/)


## Project Overview

In the e-commerce industry, product returns represent a massive financial loss in reverse logistics and contribute significantly to environmental degradation. 

## 📊 Dataset
**Size:** 5,000 records × 23 features

## Dataset Features
The analysis was performed on `returns_sustainability_dataset.csv`. Key data domains include:
* **Customer & Orders:** `Order_Quantity`, `Days_to_Return`, `Return_Reason`.
* **Logistics & Transactions:** `Shipping_Method`, `Payment_Method`, `Product_Category`.
* **Financial Impact:** `Product_Price`, `Order_Value`, `Return_Cost`, `Profit_Loss`.
* **Sustainability Metrics:** `CO2_Emissions`, `Packaging_Waste`, `CO2_saved`, `Waste_avoided`.

### Features Overview

| Category | Features |
|----------|----------|
| **Order Information** | Order_ID, Order_Date, Order_Value, Shipping_Method, Payment_Method |
| **Product Details** | Product_ID, Product_Category, Product_Price, Order_Quantity, Discount_Applied |
| **Customer Info** | User_ID, User_Age, User_Gender, User_Location |
| **Return Data** | Return_Status, Return_Reason, Days_to_Return, Return_Cost |
| **Sustainability Metrics** | CO2_Emissions, Packaging_Waste, CO2_Saved, Waste_Avoided, Profit_Loss |


### Data Statistics

| Metric | Value |
|--------|-------|
| Total Records | 5,000 |
| Returned Orders | 1,450 (29%) |
| Not Returned | 3,550 (71%) |
| Missing Values | 0 |
| Product Categories | 5 (Clothing, Electronics, Books, Toys, Home Appliances) |


### Key Data Insights

- **Product Price Range:** $100 - $2,000
- **Order Value Range:** $52 - $9,827
- **Days to Return:** 0-60 days
- **Return Cost:** $0-$200
- **CO2 Emissions:** 1.0 - 2.0 kg

### Return Reasons
- Size Issue
- Quality Issue
- Wrong Item
- No Return
- Item Not as Described

### Product Categories
- Clothing
- Electronics
- Books
- Toys
- Home Appliances

## 📁 Project Structure

```
E-Commerce-Product-Return-Sustainability-Prediction/
├── README.md                          # Project documentation
├── E_Commerce_return.ipynb            # Main analysis & ML pipeline
│   ├── Data Loading & Exploration
│   ├── Exploratory Data Analysis (EDA)
│   ├── Data Preprocessing & Feature Engineering
│   ├── Model Training & Evaluation
│   └── Sustainability Impact Analysis
└── returns_sustainability_dataset.csv # Dataset (reference)
```

## Methodology

1. Data Loading and Initial Inspection: Loaded the dataset and performed initial checks on its structure, data types, and missing values.

2. Data Cleaning and Preprocessing:Cleaned column names by stripping whitespace.

3. Standardized string values in object-type columns.

4. Created a binary target variable is_returned.

5. Converted Order_Date to datetime objects.

6. Selected relevant features and applied one-hot encoding to categorical features (Shipping_Method, Payment_Method, Product_Category).

7. Split the data into training and testing sets and scaled numerical features using StandardScaler.

8. Exploratory Data Analysis (EDA):Visualized the distribution of product returns.

9. Calculated and displayed the overall return rate.

10. Analyzed product price distribution by return status using histograms.

11. Examined return percentages across different product categories.

12. Generated a correlation matrix for numerical features.

13. Compared financial metrics (Order_Value, Return_Cost, Profit_Loss) by return status using box plots.

14. Investigated the distribution of Days_to_Return for returned products.

15. Created scatterplots to visualize relationships between numerical variables (Product_Price vs Order_Quantity, Order_Value vs Profit_Loss, CO2_Emissions vs Packaging_Waste), colored by return status.

16. Machine Learning Implementation:Baseline Random Forest: Trained and evaluated a RandomForestClassifier with balanced class weights.

17. Logistic Regression Tuning: Performed hyperparameter tuning using GridSearchCV with RepeatedStratifiedKFold to optimize C, solver, and penalty, then evaluated the best model.

18. XGBoost Tuning: Tuned XGBoostClassifier using GridSearchCV to optimize n_estimators, max_depth, learning_rate, and subsample, considering class imbalance with scale_pos_weight.


## Model Performance (Accuracy Report)
| Model	| Accuracy Score |
|-------|----------------|
| Baseline Random Forest |	0.6900 |
| Tuned Logistic Regression	| 0.6040 |
| Tuned XGBoost	| 0.5940 |

## Recommendations

1. **Risk-Based Pricing:** Apply dynamic pricing to high-return categories
2. **Quality Improvements:** Focus on Clothing category (highest return rate)
3. **Customer Verification:** Implement stricter verification for high-risk profiles
4. **Eco-Friendly Packaging:** Invest in sustainable returns process given environmental impact
5. **Early Intervention:** Use predictive model to proactively contact customers about high-return items

## Key Findings
1. **Category Trends:** Initial EDA revealed that certain categories, particularly "Clothing", exhibit significantly higher return rates.
   For example, Clothing category showed a higher return rate.
   
2. **Model Performance:** The tuned XGBoost and Logistic Regression models demonstrated notably improved **F1-Scores** compared to the baseline, proving the effectiveness of the hyperparameter tuning in handling imbalanced data.
Confusion matrices provided a detailed breakdown of model performance, highlighting areas where models predict correctly or incorrectly for both returned and not-returned items.

3. **Actionable Visuals:** Scatterplots successfully illustrated how feature relationships shift with return status, providing actionable insights for business strategies related to pricing, promotions, and sustainable packaging.


## Dependencies
* `pandas`
* `numpy`
* `matplotlib`
* `seaborn`
* `scikit-learn`
* `xgboost`


## How to Run This Project
1. Clone this repository:
   ```bash
   git clone [https://github.com/himanivarshney/ecommerce-return-prediction.git](https://github.com/himanivarshney/ecommerce-return-prediction.git)

2. Navigate to the project directory:
    cd ecommerce-return-prediction
   
3. Install the required dependencies:
    cd ecommerce-return-prediction
   
4. Ensure returns_sustainability_dataset.csv is in the root directory (or /content/ if using Google Colab).

5. Open the Jupyter Notebook to view the full pipeline:
   jupyter notebook ecommerce_returns_analysis.ipynb


If you find this analysis interesting or have questions about the methodology, feel free to connect with me on LinkedIn!
