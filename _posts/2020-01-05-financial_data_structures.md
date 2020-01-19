# Financial Data Structures

Our goal is to obtain a well structured dataset so that we could apply machine learning techniques to our investment strategy.
Although financial data may come in many forms (fundamental data, technical analysis, analyst, or even satelite images), the standard data most commonly used is the OHLCV Time Bar. Here, for a fixed time interval, for example 5 minutes, we sample the data to obtain the prices for the first, maximum, minumum, and last transactions along with the total volume traded in that 5 minute interval.

In finance, we would like to begin with raw unstructured data. This way we are more likely to make discoveries others aren't aware of and try and capitalize. So instead of considering time bars, we could go straight to the source of the data: the ticks. Each individual transaction of a financial security defines what is known as a tick. Each tick contains the price of the transaction, the volume exchanged, and a timestamp. From this data, sampling for a fixed time recovers time bars, however there are better ways analyze the data.

Sampling with respect to fixed time intervals can create bars with a disproportional amount of ticks per bar. During periods of high trading activity (market open), time bars group too many ticks into a single bar, effectively under-sampling the data. Similarly, during periods of low trading activity, we create a lot of bars containing almost no new information. Mathematically, prices sampled at constant time intervals are known to violate assumptions needed by common models such as serial correlation, heteroscedasticty, and normality of returns.

Instead of sampling with respect to a fixed amount of time passed, we could could consider sampling every time a fixed number of ticks occur, a fixed amount of volume is exchanged, or a fixed amount of dollars value exchanged.
Let's compare the statistical properties of different bar types created by tick data obtained from Bitcoin, everyones favorite cryptocurrency.

## Financial Data Structures

**Tick, Volume, Dollar Bars**
The idea of tick bars, is to sample every time a fixed amount of have occured, for example 100-tick bars. Each tick however can contain wildly varying volumes. For example, you could have 1 tick buying 100 AAPL stocks or you could have 100 ticks each buying 1 AAPL stocks. This order fragmentation brings some arbitrariness to the amount of ticks we decide to have per bar. Instead we can sample after a predetermined amount of volume has been exchanged. Sampling this way we can incorporate interactions between price and volume. Time bars for instance are made completely independent of volume. Volume is commonly used as a technical indicator.

Dollar bars, instead, sample everytime a fixed amount of money is exchanged.


**Informations Bars**
Tick Bars
Run Bars





## Event Based Sampling

**Strucutural Breaks**

CUSUM Tests

**Entropy Feautures**

Shannons Entropy

**Microstructure Features**

Price Sequences, Strategic Trade Models, Sequential Trade Models



Once we have these events sample, we can let our ML algorithms determine whether we should consider taking a position and if we should, how much.

## Labeling

**Triple Barrier Method**

**Meta-Labeling**

**Sample Weights**
