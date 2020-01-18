# Machine Learning in Finance
Every transaction of a financial security defines what is known as a tick. For each tick we record the price, volume, and the time of the transaction. It is common in finance to sample from this tick data whenever a fixed amount of time has passed. For example, long term investors often sample data in 1 day intervals while high frequency traders look at data sampled every minute or even seconds. Data sampled this way is referred to as time bars and is the most common used data when analyzing prices. Each bar contains the price of the first tick, last tick, and the maximum and minimum price for ticks during that time period, known as Open, High, Low, Close, Volume (OHLCV) data, and the sum of the volume of all the ticks considered in the bar.
Sampling with respect to fixed time intervals, however, can create bars with a disproportional amount of ticks per bar. During periods of high trading activity, time bars group too many ticks into a single bar, effectively under-sampling the data. Similarly, during periods of low trading activity, we create bars a lot of bars containing almost no new information. Worst of all, prices sampled at constant time intervals are known to violate assumptions needed by common models such as stationarity and normality.
Instead of sampling with respect to a fixed amount of time passed, we could could consider sampling a fixed number of ticks, a fixed amount of volume, or a fixed amount of dollars exchanged. Let's compare the statistical properties of different bar types created by tick data obtained from Bitcoin, everyones favorite cryptocurrency.

## Financial Data Structures

**Tick, Volume, Dollar Bars**

**Informations Bars**


## Event Based Sampling

**Strucutural Breaks**

CUSUM Tests

**Entropy Feautures**

Shannons Entropy

**Microstructure Features**

Price Sequences, Strategic Trade Models, Sequential Trade Models


## Labeling

**Triple Barrier Method**

**Meta-Labeling**

**Sample Weights**
