# Day 1 Capstone

[**csv: all files in pokemon directory**](https://github.com/dave-melillo/advanced_powerbi/tree/main/data/pokemon)<br>
[**pbix: d1_capstone.pbix**](https://github.com/dave-melillo/advanced_powerbi/blob/main/pbix_files/d1_capstone.pbix
)

In this capstone project, you will work with Pokémon trading card sales data to build a Power BI report. The project is designed to reinforce the concepts and skills learned on the first day of the course, covering ETL and  visualizations.

Project Objectives </br>
1. Data Import and Preliminary Inspection:</br>
    - Import the Pokémon trading card sales dataset into Power BI.</br>
    - Check the data for any missing values and outliers.</br>
    - Identify the data types of each column.</br>
    - Remove any duplicate values based on ID/transaction ID. </br>
2. Data Cleaning:</br>
   - Handle missing values, if any, using appropriate methods.</br>
   - Address any outliers as needed.</br>
   - Rename columns and format values to make the data more user-friendly.</br>
3. Data Transformation and ETL:</br>
   - Append Q1, Q2 and Q3 sales into one total pokemon_sales query.</br>
   - Create a relationship between the sales data and the Pokemon data. </br>
   - Create a conditional column in the Pokemon query to identify Pokemon with a Total > 500 as Powerful Pokemon. </br>
   - Create an aggregate table which calculates total sales per Pokemon and then Merge that total sales number into the Pokemon query. There should now be a “total_sales” figure next to each Pokemon. </br>
4. Basic Visualizations:</br>
   - Create Card charts and KPIs for all basic sales metrics; count and amount sold. </br>
   - Create a line chart to visualize the trend of total sales over time.</br>
   - Build a bar chart to display the top-selling Pokémon by Type 1. </br>
   - Generate a pie chart to show the distribution of sales by Generation.</br>
5. Advanced Visualizations:</br>
   - Design a correlation matrix heatmap to explore relationships between Pokemon attributes and their total_sales. </br>
   - Create a matrix table visualization to display detailed information about the top-selling cards.</br>
   - Pick total_sales and an additional attribute from the Pokemon query and use them in a Scatter Plot to understand the relationship. </br>
6. Report Layout and Design:</br>
   - Organize your report with appropriate chart titles and design. </br>
   - Format visuals, colors, and fonts to make your report visually appealing.</br>
   - Challenge: Include a filter and build a new measure</br>

