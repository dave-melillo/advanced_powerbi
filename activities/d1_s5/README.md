# Student Do: Advanced Visualizations

[**csv: all files in fin_serv_accounts directory**](https://github.com/dave-melillo/advanced_powerbi/tree/main/data/fin_serv_accounts)<br>
[**pbix: d1_s5_student.pbix**](https://github.com/dave-melillo/advanced_powerbi/blob/main/pbix_files/d1_s5_student.pbix
)

1. For the advanced visuals we will be creating a new page for each visual, unlike the core visuals which we put together on one page. </br>
2. Lets start by creating a scatter chart</br>
    a. Using the accounts query, put average of account_users on the X axis and average of balance on the Y axis. Put state on the legend shelf. </br>
    b. Your chart should look like something below. </br>
        ![Alt Text](https://github.com/dave-melillo/advanced_powerbi/blob/main/activities/d1_s5/images/1.png) <br>
3. Next lets create a funnel chart</br>
    a. Using the accounts query put account_tier on the Category shelf and put the Sum of balance on the Values shelf. </br>
    b. Challenge: Cycle through other categorical attributes on the Category shelf to see how the visual changes. Created date is especially interesting!</br>
    c. Your chart should look like something below. </br>
        ![Alt Text](https://github.com/dave-melillo/advanced_powerbi/blob/main/activities/d1_s5/images/2.png) <br>
4. Next is a waterfall chart</br>
    a. Using the accounts query put account_tier on the Category shelf and put Sum of Balance on the Y axis. </br>
    b. Your chart should look like something below. </br>
    ![Alt Text](https://github.com/dave-melillo/advanced_powerbi/blob/main/activities/d1_s5/images/3.png) <br>
5. Matrix Charts and Hierarchies</br>
    a. Create a Matrix visualization. </br>
    b. Drag the state and account_tier fields from the accounts query to the Rows shelf. This creates a hierarchy which nests account_tier under state.</br>
    c. Drag Sum of Balance and Sum of account_users to the Values shelf. </br>
    d. Your chart should look like something below. Explore the power of hierarchies by expanding each state value to expose the tier metrics per state in a Pivot style chart. </br>
    ![Alt Text](https://github.com/dave-melillo/advanced_powerbi/blob/main/activities/d1_s5/images/4.png) <br>
6. Maps</br>
    a. There are few different maps you can create in Power BI: Map, Filled Map and ArcGIS Maps for Power BI. This demo will use ArcGIS Maps for Power BI. </br>
    b. Drag State from the states query to Location and Sum of account_users to the Size shelf. </br>
    c. Your chart should look like something below</br>
    ![Alt Text](https://github.com/dave-melillo/advanced_powerbi/blob/main/activities/d1_s5/images/5.png) <br>
7. Custom visuals with R & Python</br>
    a. R</br>
        i. By default, Power BI Desktop doesn't include, deploy, or install the R engine. To run R scripts in Power BI Desktop, you must separately install R on your local computer. You can download and install R for free from many locations, including from the CRAN Repository. The current release of R scripting in Power BI Desktop supports Unicode characters and spaces (empty characters) in the installation path.</br>
        ii. From the Power BI Desktop menu, select File > Options and settings > Options.</br>
        iii. On the left side of the Options page, under Global, select R scripting.</br>
        iv. Under R script options, verify that your local R installation is specified in Detected R home directories and that it properly reflects the local R installation you want Power BI Desktop to use. In the following image, the path to the local installation of R is C:\Program Files\R Open\R-3.4.4\.</br>
        v. Once setup is complete, navigate to the Report View and create an R Script Visual</br>
        vi. Drag account_users and balance from the accounts queries to the Values shelf.</br>
        vii. You will be prompted with the R script editor, where you can enter the script below: </br>
        ```
                install.packages("corrplot", repos = "http://cran.us.r-project.org")
                require("corrplot")
                library(corrplot)


                M <- cor(dataset)


                corrplot(M, method = "color", t1.cex=0.6, t1.srt=45, t1.col = "black")
                
        ```
        </br>
        viii. Upon successful execution, your Report View should resemble the below image. </br>
        ![Alt Text](https://github.com/dave-melillo/advanced_powerbi/blob/main/activities/d1_s5/images/6.png) <br>
    b. Python</br>
        i. Install Python on your local machine.</br>
        ii. Enable Python scripting in Power BI Desktop.</br>
        iii. Install the pandas and Matplotlib Python libraries.</br>
        iv. You will be prompted with the Python script editor, where you can enter the script below: </br>
        ```
                import numpy as np
                import pandas as pd
                import matplotlib.pyplot as plt
                import seaborn as sns


                correlation_matrix = data.corr()


                plt.figure(figsize=(10, 8))
                sns.heatmap(correlation_matrix, annot=True, cmap='coolwarm', fmt='.2f', linewidths=.5)
                plt.title('Correlation Matrix')
                plt.show()
        ```

