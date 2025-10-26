# Cryptocurrency Trading Volume and Price Movements: An Empirical Analysis Using CoinGecko API

**Introduction** 

---

Cryptocurrencies have evolved over time from a niche digital token to a large financial asset traded globally on centralized and decentralized markets. As these markets have grown over time, a relationship between demand and investor confidence has become more and more easy to discover and point out.  (CoinGecko, 2024\)

In traditional finance, trading volume is often seen as a sign of market interest and liquidity, and follows the most basic economic principle: when volume rises, there is a volume of demand or investor confidence rises too. This project seeks to understand iif this relationship exists in the crypto world, using real-time data accessed through a public API. 

More specifically, the analysis investigates the relationship between daily trading volume and price changes for three major crypto coins: Bitcoin (BTC), Ethereum (ETH), and Cardano (ADA). The central question being:

To what extent is there a correlation between trading volume and price movements in major cryptocurrencies over the past year?

Using the API, pandas, seaborn, matplotlib and scikit-learn, this project applies standard data cleaning, visualisation, correlation and regression analysis to evaluate how trading activity reflects or reacts to general market behaviour. 

### **Data Collection Methodology**

---

Data for this analysis was collected from the **CoinGecko API**, a free and widely used platform for cryptocurrency market data that doesn’t require an API key (CoinGecko, 2024).

**API Endpoint Used:**  
`https://api.coingecko.com/api/v3/coins/{coin}/market_chart`

**Parameters:**

* `vs_currency`: USD  
* `days`: 365  
* `interval`: daily

The three cryptocurrencies were chosen to represent different tiers of the crypto ecosystem:

* **Bitcoin:** The most established and liquid cryptocurrency.  
* **Ethereum:** The leading smart contract platform.  
  **Cardano:** A smaller, research-driven blockchain.

Each API request returns two times series every day: The daily price and the daily trading volume. After aligning the dates and cleaning it, the data was processed using pandas. From the collected raw values, percentage changes in both price and volume were calculated, to see if there is a relationship between day to day market activity rather than the absolute price levels of each coin. 

Data Preparation 

The data preparation process only required one calculation , the percentage change. After converting all the timestamps mentioned above, each coins daily percentage change in price and trading volume was calculated using the standard percentage change formula:

Percent Change \=xt-xt-1xt-1 100 

---

### **Technical Methodology: Data Collection and Analysis Approach**

This research uses solely Python’s ability to extract and process market data using APIs. The script uses the python requests library to interact with the CoinGecko API. By carefully specifying parameters, being currency (USD), timeframe (365 days), our intervals, etc, the code collects all the data that we want and need to collect all the data that we want.   
After the collection is complete, Pandas is used to manipulate all the data, changing the raw API response to analysable DataFrames. The main processing stages being: Converting time timestamp data, calculating percentage changes for price and volume, merging datasets, and cleaning the data. After collecting all of this, we used statistical analysis techniques to generate our rolling correlations, regression and matrix calculations to present the data in the visualised form, using MatPlotLib and Seaborn. 

---

### **Price Trends**

The daily price data shows that all three cryptocurrencies generally move in similar directions over time. Bitcoin and Ethereum, in particular, move almost in sync , when one rises or falls, the other tends to follow. This is expected since both are large-cap assets that react similarly to macroeconomic news or investor sentiment (CoinGecko, 2024).

Cardano, however, moves with higher volatility. Its price changes are much sharper and more uneven, which makes sense because it is a small-cap asset with a lot less investors, and is a lot more sentiment based at the moment at least. 

---

**Volume Trends**

When comparing trading volumes, Bitcoin clearly dominates in overall scale, which matches its status as the most traded cryptocurrency. Ethereum’s trading volume also shows clear spikes during the same time periods as major price movements, suggesting that higher activity often comes during market volatility.(GeeksforGeeks, 2024).

Cardano’s volume, meanwhile, has more irregular peaks. Some of these spikes happen without major price movement, showing that smaller coins can have bursts of speculative trading not directly tied to value changes. In general, the trend across all three coins suggests that trading activity tends to rise when markets are moving fast , whether up or down. At the same time, it’s an important factor that Cardano is a very small coin, trading at values that are fractions to Ethereum and Bitcoink

---

**Correlation Between Price and Volume**

After calculating the daily percentage changes, the project generated a correlation heatmap using seaborn. The results show a positive but moderate correlation between price and volume for all three of the coins

**Bitcoin and Ethereum have the strongest positive correlations, meaning that when their prices change sharply, trading volumes follow in the same direction. Cardano, however, has a weaker correlation, showing that its trading volume is more speculative, matching the idea that because it is a smaller coin, there is more random volatility due to external factors.   
**---

### **Rolling Correlation**

The Rolling correlation analysis also showed us a relationship between trading volume and proce movements across the three selected cryptocurrencies. By calculating the 30 day rolling correlation, I figured out the ways volume and price interact over an extended period of time. Bitcoin and Ethereum showed interesting patterns, with their correlation coefficients fluctuating significantly through the month, and year. During periods of high market volatility, things like regular announcements and big developments, the correlation between volume and price changes would increase significantly, going as high as 0.6. 

Cardano had a completely different pattern, with more erratic correlations that reflected the fact that it is a small market cap coin, and is within a far more speculative trading environment. The cryptocurrency’s volume-price relationship for this reason didn’t align with the major market trends and big events, but rather appeared to be far more sensitive to external sentiment based factors. This analysis therefore effectively demonstrates that the relationship between price and trading volume, unlike traditional stocks, is not a predictable phenomenon, but a very complex, ever changing environment that’s influenced by many market forces that can go unseen.  

---

**Regression Analysis**

A simple linear regression was run for each coin, comparing daily price changes with daily volume changes. The regression line in each scatterplot shows the general direction of the relationship.

Bitcoin and Ethereum both show a slight upward slope, confirming that on average, days with larger volume changes are associated with larger price movements. Cardano’s line is flatter, again pointing to weaker consistency between trading activity and price direction.

Even though the R² values (strength of fit) are not very high, that’s expected , cryptocurrency markets are influenced by many other factors beyond just trading volume, such as macroeconomic news, regulation, and market sentiment.

---

### **Pairplot Analysis**

The pairplot at the end provides a compact visual of all relationships between price and volume changes across the three cryptocurrencies. The diagonal histograms show that daily changes are centered close to zero for all variables, with occasional extreme outliers , a sign of high volatility typical of crypto markets.

The scatterplots off the diagonal show that Bitcoin and Ethereum’s price movements are strongly aligned, while Cardano appears more scattered. Volume changes between coins show much weaker relationships, meaning trading activity is more independent from coin to coin.

---

### **Regression Analysis and Market Insights**

The linear regression analysis also created a quantitative lens into the relationship between trading volume and price movements, showing patterns across different currencies. For bitcoin and Ethereum, the regression models showed a slight positive slope at times, indicating that there is in fact a slight association between increasing trading volume and modest price changes in the market, suggesting that there is a subtle but somewhat meaningful connection between market activity and price dynamics. 

However, Cardano’s analysis showed a completely different lens. Having an almost completely flat regression line, the currency demonstrates how smaller cap currencies have a more speculative nature, where trading volume has a less predictable impact on price. Having lower R² values, however, proved that in all three cryptocurrencies there is an inherent unpredictability and complexity across crypto markets, where price movements are influenced by a lot more than simple trading volume. 

---

## **Conclusion**

This analysis shows that while trading volume and price movement are somewhat correlated, the relationship isn’t consistent over time. In broad terms, higher volume tends to occur during larger price swings, but not necessarily in a predictive way.

Bitcoin and Ethereum show stronger, more stable relationships between price and volume, while Cardano behaves more erratically. These results make sense when considering their market maturity and investor profiles. Bitcoin and Ethereum attract more institutional trading, whereas Cardano remains more retail-driven.

Overall, the results confirm that crypto markets still follow some traditional market patterns, like increased trading during volatility, but also show unique behaviors where speculation and external events can dominate short-term activity.

