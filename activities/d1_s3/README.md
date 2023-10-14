# Student Do: Advanced ETL with Power BI

[**csv: all files in fin_serv_accounts directory**](https://github.com/dave-melillo/advanced_powerbi/tree/main/data/fin_serv_accounts)<br>
[**pbix: d1_s2_student.pbix**](https://github.com/dave-melillo/advanced_powerbi/blob/main/pbix_files/d1_s3_student.pbix
)


1. Click ‘Get Data’ in the Home Ribbon and select Text/CSV as the source option. </br>
2. Choose the ‘recent_append’ csv file and the “Transform Data” option to navigate into the Power Query Editor. </br>
3. Now in the Power Query Editor, navigate to the recent_transactions query. </br>
    a. Remove all applied steps up to “Source”</br>
    b. Apply the “Use First Row as Headers” transformation</br>
    c. Change the data type of the date field to date</br>
    d. In the “Home” ribbon choose the “Combine” option and the “Append Queries” sub option</br>
    e. In the Append Queries dialog box choose “Two Tables” and recent_append as the value for “Table to append”</br>
    f. Add in previous transformations on the new appended data set </br>
        i. Rename date to transaction_date</br>
       ii. Add an Age field based of transaction_date</br>
       iii. Add a conditional column called transaction_category based on the type field</br>
    g. Close & Apply Changes</br>
    h. Challenge: Create a line chart with date on the X axis and amount on the Y axis from recent_transactions to confirm append</br>
4. Navigate back to the Power Query Editor to the “accounts” query</br>
    a. In the “Home” ribbon choose the “Combine” option and the “Merge Queries” sub option</br>
    b. In the “Merge” dialog box, choose “types” as the query to be merged and create an association between type_code_merged in the “accounts” query and “code” in the “types” query </br>
    c. Leave the rest of the settings as-is (reference the image below) and press OK to navigate back to the Power Query Editor</br>
    d. Now back in the “accounts” query, press the icon next to the new types field and select the min_bal and max_users options in the sub menu. Refer to image below for assistance. </br>
    e. Optionally, rename these newly Merged columns</br>
    f. Close & Apply Changes</br>
5. Navigate back to the Power Query Editor</br>
6. Duplicate the recent_transactions query</br>
7. Rename this query account_recent_transactions_summary</br>
8. In the “Transform” ribbon select the Group By option</br>
    a. In the Group By dialog box, choose Basic, account_id as the Group By column, Count as the New Column Name and Count Rows as the operation</br>
9. Duplicate the recent_transactions query</br>
10. Rename this query account_recent_transactions_sum</br>
11. In the “Transform” ribbon select the Group By option</br>
    a. In the Group By dialog box, choose Basic, account_id as the Group By column, Sum as the New Column Name, Sum as the operation and amount as the Column.</br>
12. Navigate back to account_recent_transactions_summary query, choose “Combine” from the Home Ribbon and the Merge Queries sub option</br>
13. In the Merge dialog, choose account_recent_transactions_sum as the join table and make an association between the account_id in both data sets. Leave the rest of the default configurations and press OK. </br>
14. In the new column that appears, click the icon next to the column name and choose only the Sum column to merge into account_recent_transactions_summary</br>
15. You should now have three columns in account_recent_transactions_summary. Change the name of the Count column to transaction_count and the Sum column to transaction_sum. </br>
16. Add a new conditional column called VIP_status with the following configuration</br>
17. Close & Apply Changes</br>
18. Challenge: Create a pie chart using the new VIP_status column in account_recent_transactions_summary with VIP_status as the legend and Count of account_id as the Values. </br>

