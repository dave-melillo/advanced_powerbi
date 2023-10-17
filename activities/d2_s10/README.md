# Session 10: Advanced Filtering

[**csv: all files in the stocks directory**](https://github.com/dave-melillo/advanced_powerbi/tree/main/data/stocks)</br>
[**pbix: d2_s10_student.pbix**](https://github.com/dave-melillo/advanced_powerbi/blob/main/pbix_files/d2_s10_student.pbix)</br>
[**pbix: d2_s10_student_starter.pbix**](https://github.com/dave-melillo/advanced_powerbi/blob/main/pbix_files/d2_s10_student_starter.pbix)</br>

In this exercise we will be implementing a number of filtering options in Power BI. It's important that you have some charts and graphs to use in order to confirm the filters are having the intended effect. You can opt to create your own visuals, or you can use the workbook provided as a starting point (d2_s10_student_starter.pbix). </br>

1. Page Filters</br>
- Start by opening up the Filters Panel in the Report View.</br>
- In the Filter Panel, drag GICS Sector from dim_company to the “Filters on this page” section of the Filter Panel. </br>
- Under GICS Sector in the Filter Panel, select Advanced filtering as the value in the Filter type menu. </br>
- Select “is not blank” as the value in the “Show items when the value” menu</br>
- This will filter OUT all of the records where GICS Sector is blank from this entire page. </br>
- Follow the steps above and add 2-3 more page filters.</br>

![Alt Text](https://github.com/dave-melillo/advanced_powerbi/blob/main/activities/d2_s10/images/1.png) <br>

2. Slicers</br>
  a. Dates & Numbers</br>
    - Select the Slicer option from the Visualizations Panel and drag Date from dim_date to the Field shelf</br>
    - Navigate to Format Visual sub-menu, Slicer Settings > Options and choose the Between value for Style. </br>
    - Repeat this process and create several new Slicers with different Style Options. </br>
  b. Categorical Data</br>
    - Select the Slicer option from the Visualizations Panel and drag Name from fct_stocks to the Field shelf</br>
    - Navigate to Format Visual sub-menu, Slicer Settings > Options and choose the Dropdown option.. </br>
    - Use this new Slicer to select multiple stock tickers by holding down control and selecting multiple values. </br>
3. Visual Level Filters</br>
    - Use the Treemaps in the provided workbook to filter your Report. Select different values in the Treemap to understand how your selections effect the entire report. </br>
    - Go to the Format tab on the Home Ribbon and select Edit Interactions.</br>
    - On on of the provided KPI charts, Choose the new “None” icon. </br>
    - As you adjust sliders notice how this chart remains unaffected. This is how you can create static visuals regardless of what Slicer values are selected. </br>

    ![Alt Text](https://github.com/dave-melillo/advanced_powerbi/blob/main/activities/d2_s10/images/2.png) <br>

4. Drill Through</br>
  - Create a new page in Power BI. </br>
  - On this new page, create a simple table with stock tickers and any number of columns/measures. </br>
  - In the Visualizations Pane, scroll down until you see a Drill Through section and then drag GICS Sector and Headquarters from dim_company to this section of the Visualizations Pane. </br>
  - Now navigate back to Page 1, select a value on the GICS or HQ Treemap and then right click the Visual. There should now be an option in the sub menu to Drill Through to Page 2. </br>
  - Repeat the process with multiple pages to create a user experience that allows users to drill from high level summary visuals to more detailed information on a separate Page.</br>

  ![Alt Text](https://github.com/dave-melillo/advanced_powerbi/blob/main/activities/d2_s10/images/4.png) <br>
  ![Alt Text](https://github.com/dave-melillo/advanced_powerbi/blob/main/activities/d2_s10/images/5.png) <br>
  
5. Syncing Slicers </br>
  - On Page 2, create a new Slicer with Symbol from dim_company as the Field value. </br>
  - In the Home Ribbon, select the View tab and then press the Sync Sliders option. This should make another Panel in between Filters and Visualizations visible. </br>
  - Click on the Symbol slicer, and in the new Sync Slicers Pane enter the group name “ticker” for the Slicer.</br>
  - Navigate to Page 1 and repeat the steps above for the existing Name Slicer. </br>
  - Once complete, notice how the selection on one Page carries over to the next on the now connected Slicers. </br>
  - Repeat this with other Fields and Slicers to create a unified experience for your users in Power BI reports. </br>



