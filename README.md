# Gold Price Prediction using LSTM

This project demonstrates the use of **Long Short-Term Memory (LSTM)** networks for predicting gold prices based on historical data. The model uses the last 7 days of gold price data (with 1-minute intervals) to make price predictions. This can be applied to real-time financial forecasting and trading strategies.

## Project Overview

The goal of this project is to predict future gold prices based on the historical price data, leveraging **time-series forecasting** methods. The project uses an LSTM network, which is well-suited for handling sequential data, and incorporates feature engineering to enhance the model's predictive power.

### Key Features:
- **Data Collection**: Gold price data from Yahoo Finance, with 1-minute intervals.
- **Time-Series Modeling**: LSTM used for forecasting.
- **Feature Engineering**: Includes rolling averages, lags, and trend indicators.
- **Model Evaluation**: Model performance evaluated using metrics like **Mean Absolute Error (MAE)** and **Root Mean Squared Error (RMSE)**.

## Data Source

The gold price data was fetched using the **Yahoo Finance API** via the `yfinance` package. The data includes the following columns:

- **Datetime**: Timestamp of the data point.
- **Open**: Opening price.
- **High**: Highest price during the interval.
- **Low**: Lowest price during the interval.
- **Close**: Closing price.
- **Adj Close**: Adjusted closing price.
- **Volume**: Trading volume.

### Data Period:
- **Start Date**: January 1, 2020
- **End Date**: December 24, 2024
- **Interval**: 1 minute

## Approach

1. **Data Preprocessing**:
   - The data is cleaned, missing values are handled, and new features are engineered based on historical prices.
   - Features like **Moving Averages (MA_7, MA_30)**, **Standard Deviation (Std_30)**, and **Lagged Features (Lag_1 to Lag_7)** are created to capture the temporal patterns in the data.

2. **Modeling**:
   - An **LSTM model** is built using Keras/TensorFlow.
   - The model uses the last 7 days of data to predict the price of gold for the next time step.
   
3. **Evaluation**:
   - The model's performance is evaluated using **Mean Absolute Error (MAE)** and **Root Mean Squared Error (RMSE)**.
   - **Validation and test splits** ensure that the model is evaluated on unseen data.

4. **Prediction**:
   - The trained model can be used to predict future gold prices.
## Results

After training the LSTM model, the **Mean Absolute Error (MAE)** achieved was approximately **0.001**, indicating that the model performs well in predicting the gold price.

## Future Enhancements

- **Hyperparameter Tuning**: Optimize the LSTM model's hyperparameters to improve performance.
- **Incorporate External Features**: Add other features such as economic indicators or sentiment analysis from news articles to improve predictions.
- **Real-Time Predictions**: Build a pipeline to make real-time predictions using live gold price data.
- **Backtesting and Trading Strategy**: Implement backtesting to assess how a trading strategy based on the predictions would have performed historically.

## License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

## Acknowledgements

- Thanks to **Yahoo Finance** for providing the gold price data through their API.
- Thanks to **TensorFlow** and **Keras** for making it easy to build and train LSTM models.
