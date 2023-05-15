# Mean Reversion Trading Algorithm 
## Algorithm Explanation
Mean-reversion strategies work on the assumption that there is an underlying stable trend in the price of an asset and prices fluctuate randomly around this trend. This means that a wide down movement below this trend will indicate a support level or buy signal and a big up movement will indicate a resistance level or sell signal. 

### Moving Average
The average price (trend) can be easily defined with a moving average. This algorithm uses the 21 simple moving average on closing price.

### Strategy
The algorithm will compare the stock's ratio (defined as the closing price divided by the moving average) with the percentile of all previous "ratios". If the last ratio measure is lower than the 10th percentile, the strategy will understand that the equity is oversold and send a buying signal. In contrast, if the ratio measure is higher than the 90th percentile, this will tell that the equity is overbought and a selling signal will be sent. Today, Machine learning models can allow us to clearly define the treshold for an overbought and oversold signal based on percentiles. However, I purposely decided to exclude this technique in my analysis to avoid an overfitting of the model. The best approach would therefore be trial and error. 

### Connect to an external device to receive buy/sell signals
At that time, my brokerage did not support algorithmic trading nor did it have any connected API. Thus, I used an external API called "push safer" to receive daily phone notifications to buy, sell, or hold this strategy and link its performance. 

## Backtest Conclusion
I decided to run the backtest on several equities. After analyzing the cumulative returns, I observed that this strategy worked best for equities that have high levels of volatility. In the graph you see below, the mean-reversion strategy has been performed on a 3x leveraged ETFs specialized in the semiconductor industry (SOXL and SOXS). As observed, the strategy outstandingly outperforms the buy & hold strategy with more than 250% returns over 12 months as compared to -70% for the buy & hold strategy. 

### Limitations
