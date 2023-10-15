# Session 7: Build a star schema data model in Power BI.

[**csv: all files in the stocks directory**](https://github.com/dave-melillo/advanced_powerbi/tree/main/data/stocks)<br>
[**pbix: d1_capstone.pbix**](https://github.com/dave-melillo/advanced_powerbi/blob/main/pbix_files/d2_s7_instructor.pbix
)

In this capstone project, you will work with Pokémon trading card sales data to build a Power BI report. The project is designed to reinforce the concepts and skills learned on the first day of the course, covering ETL and  visualizations.

This exercise will serve as a review, as well as an extension of some of the ETL and visualization concepts we learned yesterday, with an emphasis on facts, dimensions and data relationships.

1. Click “Get Data” in the Home Ribbon and select the all_stocks_5yr.csv file. </br>
2. Choose the “Transform Data” option to be sure all the columns are formatted correctly, there are no duplicates and that the data quality is generally good. </br>
3. This will be our main fact table, so lets rename the query fct_stocks</br>
4. Close & Apply</br>
5. Click “Get Data” in the Home Ribbon and select the constituents.csv file. </br>
6. Choose the “Transform Data” option to be sure all the columns are formatted correctly, there are no duplicates and that the data quality is generally good. </br>
7. This will be one of our dimension tables, so lets rename the query dim_company</br>
8. Now we will start to introduce DAX by creating a dim_date table using DAX expressions. </br>
9. Got to the “Modeling” tab on the Home Ribbon and choose “New Table” </br>
10. Use the expression below in order to create a new table called dim_date that is set to the min and max range of the date in our fact table. </br>

`dim_date = CALENDAR(min(fct_stocks[date]),max(fct_stocks[date]))`</br>

11. With the dim_date table selected create new columns using the expressions below.</br>
    `year = YEAR(dim_date[Date])`</br>
    `month = FORMAT(dim_date[Date],"mmmm")`</br>
    `monthnum = FORMAT(MONTH(dim_date[Date]),"00")`</br>
    `monthyear = CONCATENATE(dim_date[monthnum],dim_date[year])`</br>
If executed correctly you should be able to build a Table visual with the new table and fields you created. See the image below. 

![Alt Text](https://github.com/dave-melillo/advanced_powerbi/blob/main/activities/d2_s7/images/1.png) <br>
  
12. Now, navigate to the “Model View”
13. We want to connect the dim_ tables to our fact_ table to create a star schema. Connect dim_date to fct_stocks using the date field, and connect dim_company to fct_stocks using symbol and name. Your view should look like the image below 

![Alt Text](https://github.com/dave-melillo/advanced_powerbi/blob/main/activities/d2_s7/images/2.png) <br>