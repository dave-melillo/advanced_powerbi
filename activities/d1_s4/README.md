# Student Do: Core Visualizations

[**csv: all files in fin_serv_accounts directory**](https://github.com/dave-melillo/advanced_powerbi/tree/main/data/fin_serv_accounts)<br>
[**pbix: d1_s4_student.pbix**](https://github.com/dave-melillo/advanced_powerbi/blob/main/pbix_files/d1_s4_student.pbix
)

1. Ideally, students are starting with all of the ETL modeling steps from Session 2 and 3. </br>
2. We are going to start by creating some Card and KPI charts on a blank canvas</br>
    a. Create a Card chart with a count distinct of account_id from accounts</br>
    b. Rename the field Count of Accounts</br>
    c. Create a Card chart with a sum of balance from accounts</br>
    d. Create a Card chart with an average of users from accounts. You may need to change the data type of the users field before this is possible. </br>
    e. Create a KPI chart with sum of balance from accounts as the value and created date month as the Trend Axis. You may need to convert the created_date data type to accomplish this. </br>
    f. Create a new measure called target_balance and make it = 30000000</br>
    g. Use this measure as the target in the KPI card</br>
    h. See the image below for KPI card settings and final Card layout</br>
    ![Alt Text](https://github.com/dave-melillo/advanced_powerbi/blob/main/activities/d1_s4/images/1.png) <br>
3. Next we are going to create some line and bar charts</br>
    a. Create a line chart with created_date on the X Axis and count of account_id from accounts on the Y axis. Turn off the date hierarchy option for created_date so it shows daily account creations. Change the title of the chart to Daily Account Creations in Format Visuals > General > Title. </br>
    b. Create a stacked column chart with created_date on the X Axis , count of account_id from accounts on the Y axis and desc from types on the Legend shelf. Change the title of the chart to Daily Account Creations by Type in Format Visuals > General > Title. </br>
4. Time to create a pie/donut chart</br>
    a. Create donut chart withaccount_tier from accounts on the Legend shelf and count distinct account_id from accounts on the Values shelf. </br>
    b. Change the title of the chart to Account Type Distribution in Format Visuals > General > Title. </br>
    c. Your report should look like the below image.</br>
    ![Alt Text](https://github.com/dave-melillo/advanced_powerbi/blob/main/activities/d1_s4/images/2.png) <br>
5. Finally lets add a table with some details to finish off our report</br>
    a. Create a Table visual and add created_date, state, balance, account_users and account_tier from accounts. Also add desc from types. </br>
    b. Adjust the column widths manually until the entire width of the Table frame is filled. </br>
    c. Your report should look like the below image. </br>
    ![Alt Text](https://github.com/dave-melillo/advanced_powerbi/blob/main/activities/d1_s4/images/3.png) <br>





