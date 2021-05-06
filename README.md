# Stock-price-anomaly-detection-with-LSTM-autoencoder

## Data:
The historical stock price of Apple Inc. was downloaded from Yahoo Finance through the following link: https://finance.yahoo.com/quote/AAPL/history?p=AAPL \
A downloaded copy can be accessed through: 
https://raw.githubusercontent.com/huyenng1220/cmpe258/main/AAPL.csv

## Requirements:
This code has been tested in JupyterNotebook (6.0.3) using Python 3.8.3 through Anaconda (4.9.2)\
Libraries needed include:
* Tensorflow (tested in version 2.3.1)
* Sklearn (tested in version 0.23.1)
* Numpy (tested in version 1.18.5)
* Pandas (tested in version 1.0.5)
* Matplotlib (tested in version 3.2.2)
* Plotly (tested in version 4.14.3)

## Implementation
1. Download the JupyterNotebook from this github
2. If needed, download and install Anocando following the link: https://docs.anaconda.com/anaconda/install/
3. Open the downloaded notebook locally and install all necessary packages. If needed use the below code to install packages:\
import sys \
!{sys.executable} -m pip install packagenamehere 
4. run the notebook locally

## Abstract
Contributors: Zhixuan Qin, Xuan Shi, Huyen Nguyen, Jinjuan Shi

LSTM is a popular tool to analyze time-series data and can be used to detect abnormal data in sequences of time. This work aims to detect anomalies in the time series data of Apple company’s historical stock price with a LSTM autoencoder approach. In this case, LSTM was built with an encoder-decoder structure, which configured to read the input sequence, encode it, decode it, and recreate it. The performance of the model was evaluated based on the model’s ability to recreate the input sequence. We selected the period of 2014-06-10 to 2020-08-27 as the target time period because there was no stock split happened in between. We further segmented the period of 2014-06-10 to 2019-12-31 as the training period, and the period of 2020-01-01 to 2020-08-27 as the testing period. Time sequences of prior 30 days were used to train and predict the price of the following date. We made the assumption that all of the training data were considered as normal data points. As a result, the maximum value of the mean absolute error loss was considered as a threshold for abnormly detection. Any test data with mean absolute error loss higher than this threshold was considered as an abnormal time point. Our model detected a total of 56 abnormal data points that lied mostly in the March, July and August of 2020. It indicated that at the beginning of the COVIA outbreak (March 2020), the stock price dropped abnormally. Later in July and August, the stock price slight dropped initially and significantly increased in the end.

## References
https://towardsdatascience.com/step-by-step-understanding-lstm-autoencoder-layers-ffab055b6352 \
https://engineering.taboola.com/anomaly-detection-using-lstm-autoencoder/ \
https://towardsdatascience.com/time-series-of-price-anomaly-detection-with-lstm-11a12ba4f6d9 \
https://www.linkedin.com/pulse/stock-market-prediction-anomaly-detection-using-deep-learning-gupta/

