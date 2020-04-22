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
