# S-P-500-Index-Price-Prediction-Model
This Baseline Machine Learning model helps in predicting tomorrow's S&P 500 index price on trading days using historical data.

**How I built the Model:**
1. **Import Necessary Libraries**: Import the required libraries, including pandas, yfinance, matplotlib, and sklearn.

2. **Load or Download S&P 500 Data**: Check if the "sp500.csv" file exists. If not, download historical S&P 500 data using the `yfinance` library and save it as "sp500.csv."

3. **Data Preprocessing**: Perform data preprocessing tasks such as dropping unnecessary columns ("Dividends" and "Stock Splits") since these are only useful if u want to check the individul stock price and then create a new column "Tomorrow" that contains the next day's closing price.

4. **Define Predictors and Target Variable**: Define the features (predictors) for training the model, including various rolling averages and trend columns based on different horizons.

5. **Train a Random Forest Classifier**: Initialize a Random Forest Classifier(I personally thought this would be a great ML model for this situation because Random Forest are   resistant to overfitting I mean they can overfit butit is harder for them to overfit than it is for other models and they reun quickly) with specified hyperparameters (n_estimators=200, min_samples_split=50, random_state=1). Split the data into training and testing sets, and fit the model using the training data.

6. **Make Predictions**: Predict the target variable ("Target") for the test data using the trained model. Convert the predicted probabilities to binary predictions by setting a threshold of 0.6.(Just to be more confident)

7. **Evaluate Model Performance**: Calculate the precision score of the model using the predictions and the actual target values. Print the precision score and the distribution of target values and predicted values.

8. **Backtest the Model**: Perform a rolling window backtest. Iterate over the data, training the model on historical data, and making predictions for future data segments. Perform the backtest using different horizons (2, 5, 60, 250, 1000) and create new predictors based on rolling averages and trends. Drop rows with NaN values.

9. **Improve Model Predictions**: Modify the `predict` function to use the predicted probabilities instead of binary predictions. Set a threshold of 0.6 to convert probabilities to binary predictions. Perform another backtest using the updated `predict` function and the new predictors.

10. **Evaluate Improved Model Performance**: Calculate the precision score of the improved model using the predictions and the actual target values. Print the precision score and the distribution of target values and predicted values.







