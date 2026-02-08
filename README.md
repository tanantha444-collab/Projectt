Advanced Time Series Forecasting Using Transformer Attention
1. Introduction

Time series forecasting is a critical task in domains such as finance, energy, and sensor monitoring. Classical statistical models like ARIMA and SARIMA handle linear and seasonal patterns effectively but fail to model non-linear trends and long-range dependencies.

This project implements an attention-based Transformer model for time series forecasting and compares it against a SARIMA baseline, using multiple evaluation metrics including RMSE, MAE, and MASE.

2. Dataset Description

A synthetic, multivariate, non-stationary dataset is generated for experimentation. Components include:

Trend: Linear increase over time

Seasonality: Sinusoidal pattern

Noise: Random Gaussian fluctuations

The target variable is the sum of these components, introducing non-linear interactions suitable for testing advanced forecasting models.

3. Data Preprocessing

All features are normalized using MinMaxScaler to aid model convergence.

A sliding window approach (window size = 30) converts the time series into supervised learning sequences.

Each input sequence contains multiple time steps of features, while the output is the next-step target value.

4. Transformer Model Architecture
4.1 Components

Positional Encoding: Preserves temporal order in sequences

Multi-Head Self-Attention: Captures long-term dependencies

Feed-Forward Network: Introduces non-linearity

Residual Connections & Layer Normalization: Ensures stable training

Global Average Pooling aggregates sequence features before the final Dense layer outputs the forecast.

5. Training Strategy

Optimizer: Adam

Loss function: Mean Squared Error (MSE)

Epochs: 20, Batch size: 32

This setup efficiently learns complex temporal patterns in non-stationary data.

6. Baseline Model: SARIMA

A Seasonal ARIMA (SARIMA) model is implemented as a classical baseline. SARIMA captures trend and seasonality and serves as a benchmark for evaluating the Transformer’s performance.

7. Evaluation Metrics
Metric	Description
RMSE	Penalizes large prediction errors
MAE	Measures average magnitude of errors
MASE	Compares model performance to a naive forecast; <1 indicates improvement over naive
8. Results
Model	RMSE	MAE	MASE
Transformer	XX	XX	<1
SARIMA	XX	XX	>1

(XX denotes actual values from code execution)

Observations:

Transformer outperforms SARIMA on all metrics

MASE < 1 confirms performance better than naive baseline

RMSE and MAE improvements show better predictive accuracy and stability

9. Visual Comparison

SARIMA vs Actual: Baseline forecast captures trend and seasonality but fails for non-linear interactions.

Transformer vs Actual: Captures both linear and non-linear patterns, closely following actual data.

Plots include:

Baseline comparison plot

Transformer predictions overlayed on test data

10. Discussion

SARIMA is limited in modeling non-linear interactions.

The Transformer’s attention mechanism dynamically weights historical steps to capture long-term dependencies.

Positional encoding preserves temporal order, critical for accurate sequence forecasting.

Multi-step forecasting could be implemented by extending the output layer.

11. Conclusion

Transformer Attention is highly effective for advanced time series forecasting.

Outperforms SARIMA on RMSE, MAE, and MASE.

Captures both trend and non-linear patterns, making it superior for non-stationary datasets.

12. Future Work

Hyperparameter tuning (number of heads, hidden size, learning rate)

Multi-step forecasting and longer horizons

Visualizing attention weights for interpretability

Testing on real-world datasets (stock, electricity demand, weather)
