# Ferrari Stock Prediction using ARIMAX and LSTM

## 1. Project Overview

In our project, we target to predict the future closing prices of Ferrari Stock, modeling ARIMAX and LSTM respectively.

## 2. Data Description

- Source: kaggle (https://www.kaggle.com/datasets/alehcleal/ferrari-stock-data-2015-2026)
- TimeFrame: 2015.10 to 2026.02
- Target Variable: the logarithmic closing price
- Features: Log_Price_Lag1 (Lagged Logarithmic Price), Log_Return_Lag1 (Lagged Logarithmic Return), Relative_Volume (Relative Volume), Volatility100 (100-day Rolling Volatility)

## 3. Requirements

The project is developed in a Google Colab environment. To ensure reproducibility, please use the following versions:

- Python: 3.12.13

- Core Data Science: pandas==2.2.2, numpy==2.0.2

- Visualization: matplotlib==3.10.0, seaborn==0.13.2

- Time-Series & Statistics: statsmodels==0.14.6, pmdarima==2.1.1

- Machine Learning: scikit-learn==1.6.1

- Deep Learning Framework: tensorflow==2.19.0

## 4. Key Results

The evaluation results show that ARIMAX significantly outperforms LSTM in price level prediction. Its MAE, RMSE, and MAPE are all significantly lower than LSTM, indicating that ARIMAX can more accurately track the actual closing price changes of Ferrari stock. In particular, the 1.31% MAPE indicates that ARIMAX has high price prediction accuracy during the test period. In contrast, LSTM's error rate is significantly higher, indicating its weaker ability to fit price levels under the experimental settings.

However, in terms of directional accuracy (MDA), LSTM's result is slightly higher than ARIMAX (48.40% vs 45.29%). This shows that although LSTM is not as accurate as ARIMAX in predicting actual price values, it has a slight advantage in identifying short-term price direction. However, neither model's MDA reaches a high level, indicating that their ability to predict short-term direction is relatively limited.

In summary, ARIMAX is more suitable for predicting price levels of Ferrari stock, while LSTM did not demonstrate a stronger predictive advantage over ARIMAX in this experiment.

|        | MAE (USD) |   MSE    | RMSE (USD) | MAPE (%) | MDA (%) |
| :----: | :-------: | :------: | :--------: | :------: | :-----: |
| ARIMAX |  5.6236   | 71.4574  |   8.4532   |  1.3074  | 45.2906 |
|  LSTM  |  18.9782  | 558.3661 |  23.6298   |  4.2331  | 48.4009 |