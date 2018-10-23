# Comparison

This is a dataset from an [article](https://blog.exploratory.io/is-prophet-better-than-arima-for-forecasting-time-series-fa9ae08a5851)  that compares the performance of 

* Prophet
* ARIMA
* R's Forecast package

The blog post focuses on R, but it is worthwhile making a Python specific version. The datafiles used are

* [Passenger flights in 2005 - 2006 for training](https://download2.exploratory.io/downloads/data/2005_2006_flights.csv)
* [Passenger flights in 2007 for testing](https://download2.exploratory.io/downloads/data/2007_flights.csv)

I have included these files in this directory for reference.

## Claim of article

That the following (R) SARIMA model does better than Prophet:
```R
fit_arima <- Arima(training_data_ts, order=c(1,1,0), seasonal=list(order=c(1,0,0), period=12))
```

Note the following:
1. Prophet was executed with the default parameters, no tuning was done
2. The dataset is extremely small (24 points for training, 12 for fitting).
3. Note that `auto.arima` produced a simple flat line (presumably due to lakc of data)

In particular, the dataset isn't large enough to justify using an LSTM or other neural net arch.
