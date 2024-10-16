# Sales Prediction for BigMart Stores

This project involves building a **predictive model** to estimate product sales across multiple stores using historical sales data. The aim is to understand which product and store features significantly impact sales, and how we can leverage machine learning to improve sales predictions.

## Project Overview

BigMart, a large retail company, has provided a dataset containing sales data for 1559 products across 10 stores in various locations. The goal of this project is to predict **Item_Outlet_Sales** (the total sales per product in a store) based on the given product and store attributes.

### Dataset Summary

The dataset contains **8523 rows** and **12 columns** with features related to products, stores, and sales.

- **Target Variable**: `Item_Outlet_Sales` (total sales per product at a store)
- **Number of Features**: 11 independent variables including product identifiers, product characteristics (e.g., weight, visibility), and store features (e.g., location, type, size).

### Column Descriptions
1. **Item_Identifier**: Unique product ID.
2. **Item_Weight**: Weight of the product (missing values: 17.17%).
3. **Item_Fat_Content**: Categorizes products as low-fat or regular.
4. **Item_Visibility**: Percentage of the product's display area in the store.
5. **Item_Type**: Category the product belongs to (e.g., Snacks, Dairy).
6. **Item_MRP**: Maximum retail price of the product.
7. **Outlet_Identifier**: Unique store ID.
8. **Outlet_Establishment_Year**: Year the store was established.
9. **Outlet_Size**: Size of the store (Small, Medium, High) (missing values: 28.28%).
10. **Outlet_Location_Type**: Store location (Tier 1, 2, 3).
11. **Outlet_Type**: Type of store (e.g., Supermarket, Grocery Store).

## Workflow

### 1. Data Understanding & Cleaning
- **Data Exploration**: Checked for missing values and data types.
- **Handling Missing Data**: Imputed missing values for `Item_Weight` and `Outlet_Size`.
- **Categorical Data**: Addressed inconsistent entries (e.g., merged categories in `Item_Fat_Content`).

### 2. Feature Engineering
- **One-Hot Encoding** for categorical variables like `Item_Type`, `Outlet_Location_Type`, etc.
- **Feature Selection**: Identified relevant numerical features (e.g., `Item_MRP`, `Item_Visibility`).
- **Correlations**: Plotted correlation heatmap for numerical features to understand relationships.

### 3. Modeling
- Split the data into **train (70%)** and **test (30%)** sets.
- Trained and evaluated multiple models, including:
  - **Random Forest Regressor**
  - **Gradient Boosting Regressor**
  - **XGBoost**
  - **LightGBM**

### 4. Evaluation Metrics
- **R² (Coefficient of Determination)**: Measures the proportion of variance explained by the model.
- **RMSE (Root Mean Squared Error)**: Measures prediction error.

### 5. Model Performance
- **Cross-validation**: Used 5-fold cross-validation to evaluate model performance.
- Results for the best models include:
  - **Random Forest**: R² ≈ 0.60, RMSE ≈ 1100
  - **XGBoost**: R² ≈ 0.65, RMSE ≈ 1050

## Results and Findings

The **XGBoost model** performed best in terms of both **R²** and **RMSE**, indicating a strong relationship between the input features and sales predictions. Features like `Item_MRP` and store characteristics (e.g., `Outlet_Type`, `Outlet_Location_Type`) had the most significant impact on sales.

## Further Improvements

- **Hyperparameter Tuning**: While the model achieved reasonable accuracy, further fine-tuning of parameters (e.g., learning rate, depth of trees) could improve performance.
- **Feature Engineering**: Additional derived features (e.g., store traffic, regional factors) might provide more context for sales predictions.
- **Time-based Analysis**: Incorporating temporal features like month or seasonality could enhance predictions.

## Conclusion

This project demonstrates the use of machine learning to predict sales for a large retail dataset. By exploring and engineering features, several models were trained, with **XGBoost** emerging as the best-performing model. This provides actionable insights for retail management to forecast sales and optimize product placements and store operations.
