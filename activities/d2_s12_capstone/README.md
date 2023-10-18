# Session 12: Day 2 Capstone

[**csv: all files in the netflix directory**](https://github.com/dave-melillo/advanced_powerbi/tree/main/data/netflix)</br>
[**pbix: d2_s12_capstone.pbix**](https://github.com/dave-melillo/advanced_powerbi/blob/main/pbix_files/d2_s12_capstone.pbix)</br>

# Capstone Project: Power BI Report for Netflix Data Analysis

In this capstone project, you will work with Netflix titles, user, and behavior data to build a Power BI report. The project is designed to reinforce the concepts and skills learned on the second day of the course, covering DAX, filtering, and advanced report design.

## Project Objectives

### ETL and Modeling:

1. Import Netflix titles and make any transformations/changes to the base data as needed.
2. Duplicate Netflix titles and remove all columns besides `show_id` and `cast`. Right-click `cast`, split by delimited, choose a comma, and in the advanced options toggle to Rows instead of Columns.
3. Duplicate Netflix titles and remove all columns besides `show_id` and `director`. Right-click `director`, split by delimited, choose a comma, and in the advanced options toggle to Rows instead of Columns.
4. You should now have three data objects: `netflix_titles`, `cast`, and `directors`.
5. Import `netflix_users` and `watch_stats`, making sure to do basic data quality checks and transformations as needed.
6. Associate each data object to one another using the Primary and Foreign Keys to create a star schema data model.

### Create DAX Tables, Columns, and Measures

7. Create a `date_dim` table and create new date partitions aside from the date hierarchy provided.
8. Create DAX Columns and Measures, some ideas are below:
   - Year = YEAR(watch_stats[date])
   - Month = MONTH(watch_stats[date])
   - DayOfWeek = WEEKDAY(watch_stats[date])
   - MonthYear = FORMAT(watch_stats[date], "MMM YYYY")
   - AvgRatingPerShow = AVERAGEX(SUMMARIZE(watch_stats, watch_stats[show_id]), [rating])
   - TotalViews = SUM(watch_stats[id])
   - TotalUsers = COUNTROWS(SUMMARIZE(watch_stats, watch_stats[user_id])
   - AvgRating = AVERAGE(watch_stats[rating])
   - TopNShowsRatings = TOPN(5, SUMMARIZE(watch_stats, watch_stats[show_id], "AvgRating", AVERAGE(watch_stats[rating])), [AvgRating], DESC)
   - RatingDistribution = ADDCOLUMNS(GENERATESERIES(1, 5, 1), "Rating", [Value], "Count", CALCULATE(COUNTROWS(watch_stats), FILTER(watch_stats, watch_stats[rating] = [Value]))
  
### Create Visualizations using the DAX Columns and Measures above

9. Add Page Filters, Visual Filters, and Slicers to the report.
10. Add Bookmarks, Buttons, Shapes, and Images to your report.

You should be able to answer questions such as:

**User Engagement and Activity:**

- What is the total number of views for each show and for the platform overall?
- How has user activity (views, ratings, etc.) changed over time?
- What is the average rating for each show and for the entire platform?
- Which device is the most popular among users for watching content?
- What is the most common time of day for users to watch content?
- How often do users return to the platform (user retention)?
- Are there any trends in user engagement during specific days or months?

**Content Performance:**

- What is the average rating for shows directed by specific directors?
- Are there any correlations between cast members and show ratings?
- Which shows are the most popular among users from different countries?
- What is the average rating for shows in different genres?
- How has the viewership and rating of specific shows evolved over time?
- What are the top-rated shows by user demographic (e.g., age, gender, location)?

**User Demographics:**

- What is the geographic distribution of users on the platform?
- How does user activity vary across different countries?
- What types of content are preferred by users from different countries?
- Are there any notable differences in user behavior based on the device they use?
- Are there specific user segments (e.g., age groups) that engage more with certain shows?

**Platform Performance and Trends:**

- What are the overall platform performance metrics (e.g., total views, user growth)?
- How do marketing campaigns or content releases impact user engagement?
- What is the cost of acquiring new users or retaining existing ones?
- Are there trends in terms of user churn (users leaving the platform)?
- How does the platform's performance compare to industry benchmarks?

**Business Insights and Recommendations:**

- Based on the data, which shows or content categories should be prioritized for future development?
- Are there opportunities to improve user retention or attract new users?
- What is the ROI on content production and marketing efforts?
- What are the key insights for making data-driven decisions on content acquisition and creation?

