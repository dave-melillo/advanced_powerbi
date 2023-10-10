# Student Do: Load Data from CSV source and apply basic transformations with Power Query Editor.

**csv: all files in fin_serv_accounts directory**<br>
[**pbix: d1_s2_student.pbix**](https://github.com/dave-melillo/advanced_powerbi/blob/main/pbix_files/d1_s2_student.pbix
)


1. Click ‘Get Data’ in the Home Ribbon and select Text/CSV as the source option. <br>
2. Choose the ‘accounts_base’ csv file to start with. <br>
    a. Change the name of query to accounts <br>
    b. Filter out N/A values in the state field <br>
    c. Change the Data Type of balance to Decimal or Whole Number <br>
    d. Extract Text Before Delimiter (-) in the account_tier field <br>
    e. Change the Data Type of type_code_2 to Text <br>
    f. Merge type_code_1 and type_code_2 into a new field called type_code_merged <br>
    g. Close & Apply <br>
    h. Challenge: Create a simple line chart with created_date on the X axis and Count of account_id on the Y axis. <br>
3. Click ‘Get Data’ in the Home Ribbon and select Text/CSV as the source option. <br>
4. Choose the ‘accounts_states’ csv file.<br>
    a. Change the name of the query to states<br>
    b. In the Home tab, click the Use First Rows as Headers transformation<br>
    c. Close & Apply<br>
    d. Challenge: Create a simple Filled Map with state as Locatiton and Division as Legend<br>
5. Click ‘Get Data’ in the Home Ribbon and select Text/CSV as the source option. <br>
6. Choose the ‘accounts_types’ csv file.<br>
    a. Change the name of the query to types<br>
    b. Close & Apply<br>
    c. Challenge: Create a bar chart with desc on the Y-Axis and Average of Max Users on the X-Axis<br>
7. Click ‘Get Data’ in the Home Ribbon and select Text/CSV as the source option. <br>
8. Choose the ‘recent_transactions’ csv file.<br>
    a. Rename the type field to transaction_type<br>
    b. Rename the date field to transaction_date<br>
    c. Create an Age field based on the transaction_date<br>
    d. Create a conditional column called transaction_category as configured below<br>
![Alt Text](https://github.com/dave-melillo/advanced_powerbi/blob/main/student_do/d1_s2/conditional_col.png) <br>
    e. Close and Apply<br>
    f. Challenge: Create a line chart with transaction_date on the X-Axis and Count of account_id on the Y axis<br>
10. We now have all of the data sets loaded into Power BI with basic transformations applied. It is time to create a relation amongst all of them so we can quickly and easily create new measures and visuals. <br>
11. Navigate to the Model View<br>
12. Create the following associations between queries by dragging your mouse from one object to another after highlighting the associated keys<br>
    a. accounts.state > states.State Code<br>
    b. accounts.type_code_merged > types.code<br>
    c. Accounts should already be related to recent_transactions via account_id, but if not, make the association now<br>
    d. If done correctly, your Model View should resemble the image below<br>
    e.  Challenge: Go back to the Report View and create a new page. On the new page create a Matrix visualization with states.Region and types.desc on the Rows and Sum of           accounts.balance and Sum of transactions.amount on the Values. Expand all of the subsections of the Matrix and confirm that there are values for each desc. 
 ![Alt Text](https://github.com/dave-melillo/advanced_powerbi/blob/main/student_do/d1_s2/data_model.png)
