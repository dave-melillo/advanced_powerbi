# Session 8: Core DAX

[**csv: all files in the stocks directory**](https://github.com/dave-melillo/advanced_powerbi/tree/main/data/stocks)<br>
[**pbix: d2_s8_student.pbix**](https://github.com/dave-melillo/advanced_powerbi/blob/main/pbix_files/d2_s8_student.pbix
)

In this exercise we will use what we have learned so far to create Columns and Measures using DAX. 

# DAX Columns 
You can write a DAX formula to add a calculated column to any table in your model. A calculated column formula must return a scalar or single value.</br>

Calculated columns in import models have a cost: They increase the model storage size and they can prolong the data refresh time. The reason is because calculated columns recalculate when they have formula dependencies to refreshed tables.</br>

1. Daily Price Change:</br>
Code: `Daily Price Change = 'fct_stocks'[Close] - 'fct_stocks'[Open]`</br>
Explanation: This column calculates the difference between the closing price ('Close') and the opening price ('Open') for each day, representing the daily price change.</br>
    ![Alt Text](https://github.com/dave-melillo/advanced_powerbi/blob/main/activities/d2_s8/images/1.png) <br>

2. Daily Price Change Percentage:</br>
Code: `Daily Price Change % = DIVIDE('fct_stocks'[Close] - 'fct_stocks'[Open], 'fct_stocks'[Open])`</br>
Explanation: This column computes the daily price change as a percentage by taking the difference between the closing and opening prices and dividing it by the opening price.</br>

    ![Alt Text](https://github.com/dave-melillo/advanced_powerbi/blob/main/activities/d2_s8/images/2.png) <br>

3. Daily Volume Change:</br>
Code: `Daily Volume Change = 'fct_stocks'[Volume] - CALCULATE(MAX('fct_stocks'[Volume]), PREVIOUSMONTH('fct_stocks'[Date]))`</br>
Explanation: This column calculates the change in daily trading volume by subtracting the previous month’s volume from the current day's volume. If there's no previous day's month’s, it defaults to 0.</br>

    ![Alt Text](https://github.com/dave-melillo/advanced_powerbi/blob/main/activities/d2_s8/images/3.png) <br>

4. Gain/Loss Indicator:</br>
Code: `Gain/Loss Indicator = IF('fct_stocks'[Close] >= 'fct_stocks'[Open], "Gain", "Loss")`</br>
Explanation: This column categorizes daily price movement as either a "Gain" or a "Loss" based on whether the closing price is greater than or equal to the opening price.</br>

5. Trading Day of the Week:</br>
Code: `Trading Day of the Week = WEEKDAY('fct_stocks'[Date], 2)`</br>
Explanation: This column extracts the day of the week (1 to 7, Monday to Sunday) from the date, allowing you to analyze stock performance based on the day of the week.</br>


    ![Alt Text](https://github.com/dave-melillo/advanced_powerbi/blob/main/activities/d2_s8/images/4.png) <br>

# DAX Measures

1. Average Daily Volume:</br>
Code: `Average Daily Volume = AVERAGE('fct_stocks'[Volume])`</br>
Explanation: This measure calculates the average daily trading volume.</br>
2. Total Gain Days:</br>
Code: `Total Gain Days = COUNTROWS(FILTER('fct_stocks', 'fct_stocks'[Close] >= 'fct_stocks'[Open]))`</br>
Explanation: This measure counts the total number of days with a closing price higher than the opening price.</br>
3.  Total Volume Traded on Gain Days:</br>
Code: `Total Volume on Gain Days = SUMX(FILTER('fct_stocks', 'fct_stocks'[Close] >= 'fct_stocks'[Open]), 'fct_stocks'[Volume])`</br>
Explanation: This measure calculates the total volume traded on days with gains.</br>
4. Largest Single-Day Gain:</br>
Code: `Largest Single-Day Gain = MAX(fct_stocks[Daily Price Change b])`</br>
Explanation: This measure finds the largest single-day gain.</br>
5. 30-Day Rolling Average Volume:</br>
Code: `30-Day Rolling Avg Volume = AVERAGEX( TOPN(30, 'fct_stocks', 'fct_stocks'[Date], DESC), 'fct_stocks'[Volume] )`</br>
Explanation: This measure computes the 30-day rolling average trading volume.</br>
6. Largest Intraday Price Swing:</br>
Code: `Largest Intraday Price Swing = MAXX( 'fct_stocks', 'fct_stocks'[High] - 'fct_stocks'[Low] )`</br>
Explanation: This measure calculates the largest intraday price swing.</br>



