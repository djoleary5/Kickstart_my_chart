# Kickstart_my_chart
Using advanced Excel to organize and analyze data from Kickstarter campaigns.

## Background

Over $2 billion has been raised using the massively successful crowdfunding service, Kickstarter, but not every project has found success. Of the more than 300,000 projects launched on Kickstarter, only a third have made it through the funding process with a positive outcome.

Getting funded on Kickstarter requires meeting or exceeding the project's initial goal, so many organizations spend months looking through past projects in an attempt to discover some trick for finding success. For this project, I organized and analyzed a database of 4,000 past projects in order to uncover any hidden trends.


## Steps Taken

* Used conditional formatting to fill each cell in the `state` column with a different color, depending on whether the associated campaign was successful, failed, or canceled, or is currently live.

* Created a new column O called `Percent Funded` that uses a formula `=(Ex/Dx)` to uncover how much money a campaign made towards its initial goal as a percentage and used conditional formatting to fill each cell in the `Percent Funded` column using a three-color scale. The scale starts at 0 with red, transitioning to green at 100, and blue at 200.

* Created a new column P called `Average Donation` that uses a formula `=IF(Lx=0, 0, Ex/Lx)` to uncover how much each backer for the project paid on average.

* Created two new columns, one called `Category` at Q and another called `Sub-Category` at R, which use formulas to split the `Category and Sub-Category` column into two parts.

* Created a new sheet `Category Stats` with a pivot table that analyzes the initial worksheet to count how many campaigns were successful, failed, canceled, or are currently live per **category** with a stacked column pivot chart that can be filtered by country based on the table created.

 * Created a new sheet `Sub-Category Stats` with a pivot table that will analyze your initial sheet to count how many campaigns were successful, failed, or canceled, or are currently live per **sub-category** with a stacked column pivot chart that can be filtered by country and parent-category based on the table created.
 
* The dates stored within the `deadline` and `launched_at` columns use Unix timestamps.  I created two new columns: `Date Created Conversion` that will use [this formula](http://spreadsheetpage.com/index.php/tip/converting_unix_timestamps/) to convert the data contained within `launched_at` into Excel's date format and `Date Ended Conversion` that will use [this formula](http://spreadsheetpage.com/index.php/tip/converting_unix_timestamps/) to convert the data contained within `deadline` into Excel's date format.

 * Created a new sheet `Launch Date Outcomes` with a pivot table with a column of `state`, rows of `Date Created Conversion`, values based on the count of `state`, and filters based on `parent category` and `Years` and a pivot chart line graph that visualizes this new table.
 
* Create a new sheet with 8 columns:
  * `Goal`
  * `Number Successful`
  * `Number Failed`
  * `Number Canceled`
  * `Total Projects`
  * `Percentage Successful`
  * `Percentage Failed`
  * `Percentage Canceled`
In the `Goal` column, create 12 rows with the following headers:
  * Less than 1000
  * 1000 to 4999
  * 5000 to 9999
  * 10000 to 14999
  * 15000 to 19999
  * 20000 to 24999
  * 25000 to 29999
  * 30000 to 34999
  * 35000 to 39999
  * 40000 to 44999
  * 45000 to 49999
  * Greater than or equal to 50000
Using the `COUNTIFS()` formula, counted how many successful, failed, and canceled projects were created with goals within the ranges listed above. Populated the `Number Successful`, `Number Failed`, and `Number Canceled` columns with this data and also calculated the percentage of projects that were successful, failed, or canceled per goal range.  I also created a line chart that graphs the relationship between a goal's amount and its chances at success, failure, or cancellation.

## Conclusions

### 1. Given the provided data, what are three conclusions we can draw about Kickstarter campaigns?
1.  The majority of campaigns are successful.  Looking at the colors in ‘state’ column, it appears that the majority are green(successful) and this is confirmed by our pivot table, where it shows 2185 campaigns were successful while only 1530 failed, 349 were cancelled and 50 are ongoing.
2.  The most successful categories are also the three categories with the most campaigns and were art/entertainment focused, ‘film & video’, ‘music’, and ‘theater’.  One explanation for this could be that the artist’s launching these campaigns have an existing audience who wants to see this artist create more art.
3.  The subcategory stats are very telling.  Very few subcategories have a relatively balanced mix of failed and successful campaigns.  All but two subcategories have either a significant majority of successful campaigns or a significant majority of failed (or canceled) campaigns.  For example, almost 400 of the 600 technology campaigns failed (or canceled), however all 140 or the hardware subcategory were successful.  
### 2. What are some limitations of this dataset?
One limitation of the dataset is that it does not say what/if the launchers of each campaign offered as incentives for backing their campaign.  For example, a musician may include a copy of the new album for a $10 donation and a signed copy for a $100 donation.  Film directors have offered walk-on roles in the film for donations of a certain amount. I would also be interested to know about the campaign launchers’ social media presence (number of followers, etc.).  The ability to ‘get the word’ out about the campaign may be a bigger predictor of success than the category, country, or timing of the campaign. 
### 3. What are some other possible tables and/or graphs that we could create?
We could create a table listing the outcome counts for campaigns that were staff picks and those that were not, similarly we could list the outcomes for campaigns that were spotlighted and those that were not.  It would be interesting to see if there was a correlation between success rate and staff picks/spotlight.  

