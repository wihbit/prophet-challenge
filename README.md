# Prophet Challenge
An exercise in:
- visualizing data
- data preparation for visualizations
- time series data manipulation and analysis
- feature engineering
- using Prophet's machine learning package to:  
    - fit and predict based on simple time series data
    - identify periodic/seasonal trends

## Notes
From Step 3:
```
# Create a new column in the mercado_stock_trends_df DataFrame called Stock Volatility
# This column should calculate the standard deviation of the closing stock price return data over a 4 period rolling window
```  
As far as I can tell, the code needed to satisfy this instruction is:  
`mercado_stock_trends_df['Stock Volatility'] = mercado_stock_trends_df['close'].rolling(4).std()`  
However, plotting this data produced a very different plot than the one in the starter code outputs (which I refer to often to verify that I'm doing this right), and I could not figure out why. After discussing it with the instructor, we found that I would have to include the .pct_change() method to match that plot:  
`mercado_stock_trends_df['Stock Volatility'] = mercado_stock_trends_df['close'].pct_change().rolling(4).std()`  
The instructions do not implicitly or explicitly instruct us to include .pct_change() in the code, but I used it to match the starter code's plot.