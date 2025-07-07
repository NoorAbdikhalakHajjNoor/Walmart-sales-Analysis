# walmart-sales-task
# Walmart Sales Prediction

## Project Overview
This project aims to predict weekly sales for Walmart stores using historical sales data, store attributes, and additional economic indicators. The dataset includes markdown events, holidays, consumer price index (CPI), and unemployment rates to improve forecasting accuracy.

## Dataset
- `features.csv` - Contains additional store-related data like markdowns, CPI, and unemployment.
- `stores.csv` - Contains store type and size information.
- `train.csv` - Historical sales data used for model training.
- `test.csv` - Data on which sales predictions are made.

## Data Preprocessing
- Merged datasets based on `Store` and `Date`.
- Converted `Date` to datetime format and extracted `Week` and `Year`.
- Encoded categorical variables (`Type`, `IsHoliday`).
- Handled missing values by replacing them with `0`.
- Defined `IsHoliday` as a numerical feature based on specific holiday weeks.

## Model Training
- **Algorithm Used:** XGBoost Regressor(used), Linear Regression and Random Forest.
- **Hyperparameter Tuning:** Performed randomized search to optimize `n_estimators`, `learning_rate`, `max_depth`, `subsample`, and `colsample_bytree`.
- **Evaluation Metrics:**
  - Root Mean Squared Error (RMSE)
  - Mean Absolute Error (MAE)

## Predictions and Visualization
- Used the trained model to predict sales on test data.
- Plotted **Actual vs. Predicted Sales** to visualize model performance.

## Key Insights
1. **Impact of Holidays:**
   - Sales fluctuate significantly during holiday weeks, with Thanksgiving and Christmas having the highest spikes.
   - Holiday sales impact varies across stores, indicating different regional purchasing behaviors.

2. **Store Type Influence:**
   - Larger stores (Type A) tend to generate higher sales on average compared to smaller ones (Type B and C).

3. **Feature Importance:**
   - Key factors affecting sales predictions include holiday weeks, store size, markdowns, and economic indicators like CPI and unemployment rate.

## How to Run
1. Install dependencies:
   ```bash
   pip install numpy pandas matplotlib seaborn scikit-learn xgboost
   ```
2. Place the dataset files in the project directory.
3. Run the script
4. View the visualization of actual vs. predicted sales.

## Future Improvements
- Incorporate deep learning models like LSTMs for time-series forecasting.
- Experiment with additional economic indicators and external factors.
- Optimize feature selection for better model efficiency.

