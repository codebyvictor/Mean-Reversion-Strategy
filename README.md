# Mean Reversion Trading Algorithm 
## Algorithm Explanation
Mean-reversion strategies work on the assumption that there is an underlying stable trend in the price of an asset and prices fluctuate randomly around this trend. This means that a wide down movement below this trend will indicate a support level or buy signal and a big up movement will indicate a resistance level or sell signal. 

### Moving Average
The average price (trend) can be easily defined with a moving average. This algorithm uses the 21 simple moving average on closing prices.

### Strategy
The algorithm will compare the stock's ratio (defined as the closing price divided by the moving average) with the percentile of all previous "ratios". If the last ratio measure is lower than the 10th percentile, the strategy will understand that the equity is oversold and send a buying signal. In contrast, if the ratio measure is higher than the 90th percentile, this will tell that the equity is overbought and a selling signal will be sent. Today, Machine learning models can allow us to clearly define the threshold for an overbought and oversold signal based on percentiles. However, I purposely decided to exclude this technique from my analysis to avoid any overfitting. 

### Connect to an external device to receive buy/sell signals
At the time, my brokerage did not support algorithmic trading nor did it have any connected API. Thus, I used the external API "push safer" to receive daily phone notifications to manually buy, sell, or hold this strategy, with a report of its performance. The code ran at a specific time daily on a cloud-based system. 

## Backtest Conclusion
I ran the backtest on several equities. After analyzing the cumulative returns, I observed that this strategy worked best for equities with high volatility. In the graph you see below, the mean-reversion strategy has been performed on a 3x leveraged ETF specialized in the semiconductor industry (SOXL and SOXS). As observed, the strategy outstandingly outperforms the buy & hold strategy.

### Limitations
This strategy assumes no commissions or slippage. Furthermore, higher volatility also comes with higher downside risks. As a result, one cannot entirely rely on a technical analysis strategy. Company-specific news, brand sentiment, and macro trends also need to be considered.

<p align="center">
  <img src="https://github.com/codebyvictor/Mean-Reversion-Strategy/strategy-graph.png?raw=true" alt="Sublime's custom image"/>
</p>
