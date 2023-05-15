# Mean Reversion Trading Algorithm 
## Algorithm Explanation
Mean-reversion strategies work on the assumption that there is an underlying stable trend in the price of an asset and prices fluctuate randomly around this trend. This means that a wide down movement below this trend will indicate a support level or buy signal and a big up movement will indicate a resistance level or sell signal. 

### Moving Average
The average price (trend) can be easily defined with a moving average. This algorithm uses the simple moving average 90 and a daily timeframe

### Strategy
If the price moves away from the moving average to the upside, the algorithm enters starting to open Sell/Short positions and Vice Versa if the price moves to the downside. 

### Connect to an external device for notification


## Backtest Conclusion
It can be very simple to program a trading strategy that works. If you have further ideas to improve the algorithm, feel free to fork, implement and share or contact me. Hopefully, lots of people can make a lot of money or learn something about the financial markets :-)
