
# Kickstarting with Excel

## Overview of Project

### Purpose

Louise intially reached out looking for data on fundraising campaigns to help plan out fundraising for her own play. US successful and failed kickstarters as well as a handful of Edinburgh plays were analyzed to help Louise determine the best time of year to fundraise, how successful theater campaigns have been, and how successful play campaigns have been in the past. This new set of data was requested by Louise now that she is close to her own fundraising goal. The purpose of this analysis is to compare fundraising goals, launch dates, and the overall successes or failures of these funraising campaigns. 

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date

The outcomes of fundraising campaigns for theater fundraising based on outcomes was analyzed using a Pivot Table. In order to show only data on the theater campaigns, the "parent category" was added to the filters. To get the breakdown of each month, the "years" row was added to the filters as well. The columns are made of the outcomes and all of the values are counts of the outcomes. In order to get "years" filter to mean anything, the "date created conversion" was used to fill in data for the rows. Once the Pivot Table was created, the data was filled into a line graph that maps out successful campaigns, failed campaigns, and cancelled campaigns by month. The data presents in a chart as follows: 
![Theater Outcomes vs Launch](https://user-images.githubusercontent.com/88064181/128584155-6d14de70-b82d-405f-abdb-5c67c7357617.png)
---
In terms of fundraising campaigns for plays, the data was analyzed to show how successful a campaign was based its goals of the fundraising. The data for this analysis was pulled from the 'Kickstarter' workbook by using the '=countifs' function. In order to get the total number of projects for each goal level,  the '=sum()' function was used to add across the row. Finally, an '=iferror(x/y*100,0) function was used to calculate the percentage of outcomes for each of the potential outcomes. This data set was then applied to a line chart in order to compare the outcomes for all levels of campaign goals. The line chart follows:
![Outcomes vs Goals](https://user-images.githubusercontent.com/88064181/128584274-2d47e9e7-5639-4f80-8842-1940a8de5b1d.png)

### Analysis of Outcomes Based on Goals

### Challenges and Difficulties Encountered

Wrangling this data into comprehensive worksheets and charts did not come without its challenges. Within the worksheet "Outcomes Based on Goals," the function for the perentage of successful, failed, and canceled was originally calculated as '=(d12/e12*100)', with the rows and column changing to coordinate with the proper cells. This function would have worked fine if not for a few cells that came up with the '#Div/0!' error. This issue was corrected by updating the percentage functions to read as '=IFERROR(d12/e12*100,0)'. 
---
Another challenge faced with this data again came within the "Outcomes Based on Goals" worksheet. In order to get the correct data into this worksheet from the original "Kickstarter" worksheet, a nested 'countifs' statement had to be used. This statement appeared to be working correctly until cell B11 which appeared as the value 0. The original function for this cell was '=COUNTIFS(Kickstarter!F:F,"=successful", Kickstarter!D:D, "<=44999", Kickstarter!D:D, ">40000", Kickstarter!R:R, "=plays")'. This would pull any data less than or equal to 44999 and greater than 40000 for goals.  This original function left no room for goals that were exactly 40000. To correct this error and ensure that no data was left out of this analysis, the function was updated to '=COUNTIFS(Kickstarter!F:F,"=successful", Kickstarter!D:D, "<=44999", Kickstarter!D:D, ">=40000", Kickstarter!R:R, "=plays")'. This corrected function was applied to cells B3-B12, C3-C12, and D3-D12 with their correlating category to ensure all data was included in this analysis. 

## Results

When looking at "Theater Outcomes by Launch Date" worksheet, many conclusions can be drawn. The biggest conclusion that can be drawn is that the most successful theater campaigns were launched in the month of May, followed closely by the month of June. If one does not want their fundraising cancelled, they should  launch their campaign in October, but this comes with a 43% change of the campaign failing. The 43% fail rate of October is also the highest percentage of fundraising campaigns failed throughout the year. It appears that backers are more willing the donate money in the late spring/early summer, and less likely to pledge money in the middle of fall. 
---
According to the "Outcomes Based on Goals," fundraising campaigns for plays are likely to only succeed or fail, they are never cancelled. The lower the goals for these campaigns are, the more likely they are to succeed, while campaigns with higher goals are more likely to fail. There is a slight outlier in this conclusion which is that campaigns with goals between $35000 and $44999 have more successes than failures. This outlier is based on a very small number of campaigns, though. 
---
By studying the outcomes based on goals for plays, we can draw conclusions on how to set up a fundraising campaign. Unfortunately, this dataset is very limited due to the size of this set. Only 1112 fundraising campaigns were used to draw conclusions and not a single one was cancelled. By limiting the data to only plays, valuable data about how backers pledge money and what kind of monetary goals entice them to pledge that money is lost. The data sets used for this analysis only inform us of very specific outcomes based on limiting data. While the outcome based on goals gives a snapshot on fundraising campaigns, knowing by how much goals were succeed or failed would be helpful as well as how long these fundraising campaigns were run for. 
---
In order to provide Louise with a better overview of data, many other analysises can be done on the data provided. As mentioned above, tables and charts can be created to show how much money was pledged past the original goals for the successful fundraising campaigns and how much money pledged was under the original goals for failed fundraising campaigns. The duration of successful, failed, and cancelled campaigns would also be prudents when deciding when to launch a campaing and planning how long to run a campaign before cancelling it if it does not seem to be successful. 
