Course_Project_Walmart_Time_Series_Forecast


# Walmart_Time_Series_Forecast

## Overview
This project aims to predict weekly sales for various stores of Walmart using different regression models. The dataset includes various features such as store information, markdowns, and economic indicators, allowing for a comprehensive analysis of sales trends.

## Libraries Used
- **Python Libraries**:
  - NumPy
  - Pandas
  - Matplotlib
  - Seaborn
  - SciPy
  - Statsmodels
  - Scikit-learn
  - XGBoost

## Data Preparation
### Handling Missing Values
- Missing values in the `CPI` and `Unemployment` columns were filled with their median values.
- Negative values in `MarkDown` columns were replaced with 0, and remaining missing values were also filled with 0.

### Merging Datasets
- The main dataset was merged with store and features datasets to incorporate additional context.
- The `Date` column was converted to a datetime format and set as the index.

### Outlier Detection
- Outliers were detected using Z-score and filtered from the dataset.
- Aggregate statistics for weekly sales were computed, and any rows with null values in key statistics were removed.

### Feature Engineering
- A new column, `Total_MarkDown`, was created by summing the markdown columns.
- Year, Month, and Week features were extracted from the `Date` column.

## Model Training and Evaluation
Different regression models were implemented to predict weekly sales:

1. **Linear Regression**
   - Accuracy: 91.52%
   - Metrics: 
     - MAE: 0.032
     - MSE: 0.0038
     - RMSE: 0.0618
     - R²: 0.915

2. **Random Forest Regressor**
   - Accuracy: 97.55%
   - Metrics:
     - MAE: 0.0166
     - MSE: 0.0011
     - RMSE: 0.0332
     - R²: 0.975

3. **K Neighbors Regressor**
   - Accuracy: 95.22%
   - Metrics:
     - MAE: 0.0222
     - MSE: 0.0022
     - RMSE: 0.0464
     - R²: 0.952

4. **XGBoost Regressor**
   - Accuracy: 97.41%
   - Metrics:
     - MAE: 0.0193
     - MSE: 0.0012
     - RMSE: 0.0342
     - R²: 0.974

## Visualization
Visualizations were created to compare predicted values against actual values for each model, providing insights into their performance.

## Files
- `lr_real_pred.csv`: Linear Regression predictions
- `rf_real_pred.csv`: Random Forest predictions
- `knn_real_pred.csv`: KNN predictions
- `xgb_real_pred.csv`: XGBoost predictions

## Conclusion
The Random Forest Regressor achieved the highest accuracy, making it the preferred model for predicting weekly sales. Further enhancements can include hyperparameter tuning and exploring additional features.

## Future Work
- Experiment with additional regression models and techniques.
- Perform hyperparameter optimization for existing models.
- Incorporate time series analysis for improved predictions.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

