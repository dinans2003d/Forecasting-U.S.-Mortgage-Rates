# Forecasting U.S. Mortgage Rates

Dinan Sooriyaarachchi | CS 4680 Time Series Project | May 2026

A time series forecasting project on the 30-Year Fixed Mortgage Rate, answering one question: should homebuyers wait for rates to drop, or buy now?

I pulled 55 years of weekly mortgage rate data from FRED (April 1971 to May 2026), resampled to monthly, and held out the last 12 months as a test set. Then I trained four models: Holt-Winters (baseline and tuned), SARIMA, and Prophet, ranked them by test RMSE, and used the winner to forecast the next 12 months.

The tuned Holt-Winters model won with a MAPE of 6.54%, beating SARIMA (7.37%), baseline Holt-Winters (7.50%), and Prophet (11.30%). It forecasts rates staying flat through May 2027, ending around 6.35% versus today's 6.37%. The data does not support waiting for relief.

Stack: Python, pandas, statsmodels, prophet, scikit-learn, matplotlib.

Limitations: univariate only. A stronger version would add the 10-Year Treasury, Fed Funds rate, and inflation indicators so the model can respond to macro shifts.
