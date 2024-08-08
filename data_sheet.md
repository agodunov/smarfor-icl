## Motivation
This dataset for the small educational project was created during my studies of [ML/AI at Imperial College Business School](https://www.imperial.ac.uk/business-school/executive-education/technology-analytics-data-science/professional-certificate-machine-learning-and-artificial-intelligence-programme/online//). 

The dataset has two sources:
1. [The Federal Reserve Economic Data](https://fred.stlouisfed.org/) (FRED) is an online database consisting of hundreds of economic data time series since last century. The FRED database was created and maintained by the Research Department at the Federal Reserve Bank of St. Louis. 
2. [Yahoo Finance](https://finance.yahoo.com) is the well known publicly available source of stocks, indexes and commodities, supported by Yahoo Inc.
 
## Composition
The data was downloaded from two sources and jointed by time index. Since economic indicators are released with less frequency than price, the  last known reading for that day was used. In this way, it was possible to obtain a large array of data for each trading day for the last 32 years from 1992-02-03 to 2024-07-01. Some of the metrics were normalized to make them stationary and suitable for machine learning like price normalization:
$$ pr\_0 = \frac {Price_{today} - MA_{20}}{MA_{20}} $$

## Collection process
See details in source.

## Uses, Distribution and Maintanance
The datasets are maintaned and distributed to public for economic research and educational purposes by US Federal Reserve Bank of St, Louis
