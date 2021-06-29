# INTRODUCTIONr Fingerprints

# REFERENCES
# RELATED WORK
# KEY CONTRIBUTION
* first time to aplied VAE model.
# TERMINOLOGY
* kurtosis
    * kurtosis with value of 3 = Gaussian distribution
    * kurtosis with a value > 3 is an indicator of more peaked distribution than Gaussian distribution
* autocorrelation function (ACF)
    * it is a time-domain meric that is able to quantify the stochastic process memory.

# STANDARD AND BASELINE

* dataset
    * WHO dataset 
        * reported by 210 countries and territories worldwide
* model 
    * RNN
    * LSTM
    * Bi-LSTM
    * GRU
    * variation auto encoder (VAE)

* evaluation

    * root mean square (RMSE)
    * RASLE 
        * root mean square but calculated in the log scale
    * mean absolute percentage error (MAPE)
    * mean absolute error (MAE)

# METHODOLOGY
* data exploration
    * to check asymmetry of the data distribution around the sample mean. 
        * we check kurtosis and skewness and compare to guassian 
    * to verify the nonstationary and time-dependent behavior of the time series data
        * we use autocorrelation function (ACF)
* dataset
    * use daily figure of confirmed and recovered cases collected from six 
     highly impacted countries including the following
        * eg USA, China, Australia, Spain, Italy
    * data is gathered from 22 Jan 2020 til Juan 17th, 2020
* tasks
    * time series forcasting 
        * 17 days ahead 
* evaluation
    * evaluation is applied for one-ahead forecasting  
# RESULT
