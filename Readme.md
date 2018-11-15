# Fintech: Best Time to Buy and Sell Stock with Transaction Fee
* Find the best time to buy and sell stock with transaction fee using Dynamic Programming, implementation in Python.

## Algorithm
- Use **Dynamic Programming** to compute to optimal action sequence along a give price vector.
- DP records the following at each time t:
	- optimal value of money, and
	- optimal value of stock, and
	- the previous action that lead to this optimal value
- **DP initialization:** 
	- money = original capital, and
	- stock = buy stock with original capital
- **DP recursion:**
	- calculate optimal money:
		* money = hold yesterday's money, or
		* money = sell all your stocks today
	- calculate optimal stock:
		* stock = hold yesterday's stock, or
		* stock = buy stock today with all your money
- **DP trace back:**
	- You must sell on the last day to maximize profit
	- trace the previous action that lead to this optimal value
- **Action smoothing:**
	- if previous action is the same as the current action, then the action choosen is "hold".

## Result
- Testing on the [SPY dataset](https://finance.yahoo.com/quote/SPY/history?period1=1167580800&period2=1508947200&interval=1d&filter=history&frequency=1d), **return rate is: 212.88675299365727**


## Usage:
- Use default:
```
python3 optimal_stock_action.py
```
- Run with customized dataset and transaction fee value:
```
python3 optimal_stock_action.py ./data.csv 0.01
```