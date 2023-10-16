# Session 9: Advanced DAX

[**csv: all files in the stocks directory**](https://github.com/dave-melillo/advanced_powerbi/tree/main/data/stocks)</br>
[**pbix: d2_s9_student.pbix**](https://github.com/dave-melillo/advanced_powerbi/blob/main/pbix_files/d2_s9_student.pbix
)

Let’s start by working with aggregation iterator DAX functions. Try to recreate each MEASURE using the S&P 500 stock data. </br>
1. SUMX - Calculating the total daily trade volume for each stock ticker:</br>
`Total Volume = SUMX(fct_stocks, fct_stocks[Volume])`</br>
This calculated column sums the daily trading volumes for each stock ticker in the 'fct_stocks' table.</br>
2. COUNTX - Counting the number of days when the closing price is above a certain threshold (e.g., $100):</br>
`Days Above $100 = COUNTX(fct_stocks, IF(fct_stocks[Close] > 100, 1, 0))`</br>
This calculated column counts the number of days when the closing price of a stock is above $100.</br>
3. AVERAGEX - Calculating the average daily change for each stock ticker:</br>
`Avg Daily Change = AVERAGEX(fct_stocks, fct_stocks[Close] - fct_stocks[open])`</br>
This column calculates the average daily return for each stock ticker based on the closing prices.</br>
4. MINX - Finding the minimum daily low price for each stock ticker:</br>
`Min Low = MINX(fct_stocks, fct_stocks[Low])`</br>
This column determines the minimum low price for each stock ticker.</br>
5. MAXX - Identifying the maximum daily high price for each stock ticker:</br>
`Max High = MAXX(fct_stocks, fct_stocks[High])`</br>
This calculated column finds the maximum high price for each stock ticker.</br>
6. MEDIANX - Calculating the median daily volume for each stock ticker:</br>
`Median Volume = MEDIANX(fct_stocks, fct_stocks[Volume])`</br>
This column computes the median daily trading volume for each stock ticker.</br>
7. STDEVX.P - Calculating the population standard deviation of daily closing prices for each stock ticker:</br>
`Stdev Population Close = STDEVX.P(fct_stocks, fct_stocks[Close])`</br>
This column computes the population standard deviation of daily closing prices for each stock ticker.</br>
8. STDEVX.S - Calculating the sample standard deviation of daily high prices for each stock ticker:</br>
`Stdev Sample High = STDEVX.S(fct_stocks, fct_stocks[High])`</br>
This calculated column calculates the sample standard deviation of daily high prices for each stock ticker.</br>
9. VARX.P - Determining the population variance of daily low prices for each stock ticker:</br>
`Variance Population Low = VARX.P(fct_stocks, fct_stocks[Low])`</br>
This column computes the population variance of daily low prices for each stock ticker.</br>
10. VARX.S - Computing the sample variance of daily open prices for each stock ticker:</br>
`Variance Sample Open = VARX.S(fct_stocks, fct_stocks[Open])`</br>
This calculated column calculates the sample variance of daily open prices for each stock ticker.</br>

After adding all of these DAX iterator measures you should combine them all into a table using the ‘monthyear’ of the dim_date query as the main aggregate category. See image below.</br>

    ![Alt Text](https://github.com/dave-melillo/advanced_powerbi/blob/main/activities/d2_s9/images/1.png) </br>


Let’s continue by creating some RANK measures, leveraging several of the aggregate iterator measures we made in the previous step. </br>
```
Rank by Volume:
Stock Volume Rank = 
RANKX(
    ALL('fct_stocks'[name]),
    fct_stocks[Total Volume]
)
```

```
Rank by Close:
Stock Close Rank = 
RANKX(
    ALL('fct_stocks'[name]),
    fct_stocks[Total Close]
)
```
```
Rank by Avg Close:
Stock Avg Close Rank = 
RANKX(
    ALL('fct_stocks'[name]),
    fct_stocks[Total Avg Close]
)
```
You should be able to combine all of these ranks into one table, aggregate by fct_stocks name or ticker. See below to confirm. </br>

    ![Alt Text](https://github.com/dave-melillo/advanced_powerbi/blob/main/activities/d2_s9/images/2.png) </br>


Finally, let’s see some examples of using the CALCULATE functions with advanced FILTERS. This may require Merging some of the attributes from dim_company into fct_stocks.</br>

```
Total Volume FAANG =
CALCULATE(
   SUM('fct_stocks'[Volume]),
   FILTER('fct_stocks', 'fct_stocks'[Name] IN {"FB", "AAPL", "AMZN", "NFLX", "GOOGL"})
)
```
```
Avg Close Price InfoTech =
CALCULATE(
   AVERAGE('fct_stocks'[Close]),
   FILTER('fct_stocks', 'fct_stocks'[Sector] = "Information Technology")
)
```
```
Max Daily Return Energy =
CALCULATE(
    MAXX(
        FILTER('fct_stocks', 'fct_stocks'[Sector] = "Energy"),
        'fct_stocks'[Close] / 'fct_stocks'[Open] - 1
    )
)
```
```
Total Volume Recent IPO =
CALCULATE(
   SUM('fct_stocks'[Volume]),
   FILTER('fct_stocks', YEAR('fct_stocks'[date_added]) >= YEAR(TODAY()) - 5)
)
```




