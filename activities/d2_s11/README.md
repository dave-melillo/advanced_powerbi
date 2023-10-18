# Session 10: Advanced Filtering

[**csv: all files in the stocks directory**](https://github.com/dave-melillo/advanced_powerbi/tree/main/data/stocks)</br>
[**pbix: d2_s11_student.pbix**](https://github.com/dave-melillo/advanced_powerbi/blob/main/pbix_files/d2_s11_student.pbix)</br>

Time to take everything we’ve learned about visualizations, filters and design to create a S&P 500 Stock Explorer report!</br>

1. On the Home Ribbon, go to the View tab. Change the theme of the report to “Innovate” and check the box to show Gridlines. This will make it easier to visually design our report moving forward. </br>
2. On the Home Ribbon, go to the Insert tab. Insert a Text Box to create a title for the report. The title should be something like “Stock Explorer” at 40 point font. Feel free to get creative with text formatting.</br>
3. Create three Cards stacked on top of each other. They should be roughly 1x2 gridlines. You can pick from any of the metrics we create to populate each of the cards. </br>Navigate to the Format your visual menu > Callout value > and adjust the font to 15. Your report should resemble below at this point. </br>

![Alt Text](https://github.com/dave-melillo/advanced_powerbi/blob/main/activities/d2_s11/images/1.png) <br>

4. Create a line chart. It should be roughly 9x3 gridlines. Drag date from fct_stocks to the x-axis, close to the Y axis and Total Volume to the second Y axis. </br>
5. Create another line chart. It should be roughly 9x3 gridlines. Drag date from fct_stocks to the x-axis, close to the Y axis. In the analytics menu turn the Trend Line ON. </br>
6. Create another line chart. It should be roughly 9x3 gridlines. Drag date from fct_stocks to the x-axis, volume to the Y axis. In the analytics menu turn the Trend Line ON. </br>
7. Stack these line charts directly on top of one another. </br>
8. On the Home Ribbon, select the View tab and the Selection Show Panels and Bookmark Show Panel  options. There should now be a new panels next to Filters.</br>
9. In the Selections panel > Layer Order, take turns hiding the three line charts and creating a bookmark. The idea is that each bookmark should only show one chart at a time. </br>
10. Create three buttons with Actions mapped to the Bookmarks created in the previous step. In the Format panel, navigate to Button > Text, turn it on and then type a title for each button. Ctrl + Click each button to make sure you have achieved the desired effect.</br>
![Alt Text](https://github.com/dave-melillo/advanced_powerbi/blob/main/activities/d2_s11/images/2.png) <br>

11. Create a Matrix chart with GICS Sector and Symbol on the Rows and 4-5 measure as values. Click on the different GICS Sector values to demonstrate you can use the chart as a filter. With the Matrix chart selected, navigate to the Filter panel and exclude Blank GICS Sector values from the chart. </br>
12. With the Matrix chart still selected navigate to the Visualization panel. Next to each Value is a down arrow. Click the down arrow for the first Value.  In the presented sub menu choose conditional formatting > background color and choose the default. </br>
13. Repeat this process with the next Value but instead choose Font Color and accept defaults.</br>
14. Repeat this process for the  next two Values but instead choose Data Bars and accept defaults.</br>
15. For the last Value, click the down arrow then choose Add Sparkline. Leave the Value on Y-Axis and choose date for the X-Axis. Your chart should resemble below. </br>
![Alt Text](https://github.com/dave-melillo/advanced_powerbi/blob/main/activities/d2_s11/images/3.png) <br>

16. Create a Treemap with GICS Sub-Industry as the Category and Sum of Close as the value. Change the title and filter out all blank Sub-Industry values for this chart only. </br>
17. Insert a line shape and rotate it 270 degrees to create a border between the visualizations and the blank space on the left of the report reserved for the slicers. Your report should resemble below</br>
![Alt Text](https://github.com/dave-melillo/advanced_powerbi/blob/main/activities/d2_s11/images/4.png) </br>

18. Time to create so Slicers. Most of our slicers will be focused on date/time since our visualizations also function as filters. </br>
19. Create a slicer, use date as the field and navigate to Format your visual > Visual > Slicer Settings > Between. </br>
20. Create a slicer, use date as the field and navigate to Format your visual > Visual > Slicer Settings > Relative.</br>
21. Create a slicer, use date as the field and navigate to Format your visual > Visual > Slicer Settings > After.</br>
22. Create a slicer, use date as the field and navigate to Format your visual > Visual > Slicer Settings > Before.</br>
23. Create a slicer, use Sector as the field and navigate to Format your visual > Visual > Slicer Settings > Drop Down.</br>
24. Create a slicer, use Symbol as the field and navigate to Format your visual > Visual > Slicer Settings > Drop Down.</br>
25. On the Home Ribbon, navigate to the Insert tab, choose Image and insert the provided S&P 500 logo. Resize as needed. Your finished product should resemble below. </br>
![Alt Text](https://github.com/dave-melillo/advanced_powerbi/blob/main/activities/d2_s11/images/5.png) <br>

26. Challenge: </br>
- Create a MAP chart based off of the HQ provided in dim_company. </br>
- Add borders to visuals. </br>
- Create a Drill Through page. </br>
- Add more borders to define the shape of the report. </br>
- Add more charts to the line chart carousel. </br>

