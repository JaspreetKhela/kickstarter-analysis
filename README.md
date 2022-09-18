# Kickstarting with Excel

## Overview of Project

### Purpose
The purpose of this analysis was to determine the outcomes of theater Kickstarter campaigns based on the months in which they were launched and the percentage of successful, failed, and cancelled theater play Kickstarter campaigns based on their respective funding goals. Broadly speaking, this analysis was intended to shed light on how the launch month of a campaign and how the size of a campaign's funding goal would impact the success of the campaign.

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date
This analysis was conducted by:
* Separating the "category" and "subcategory" values from one column into separate columns;
* Converting Unix timestamps into legible dates stored in the "date_created_conversion" and "date_ended_conversion" columns;
* Extracting the years from the legible date columns;

_____

<img width="1440" alt="Screen Shot 2022-09-18 at 10 17 36 AM" src="https://user-images.githubusercontent.com/80941606/190911849-8080a1a5-0951-47ac-82df-28844e21e26d.png">

**Image 1.0**: Raw Kickstarter data.
_____

* Creating a PivotTable in a new sheet titled "theater_outcomes_by_launch_date" by using the "outcomes" as columns, "date_created_conversion" as rows, count of "outcomes" as values, and the "category" and "years" filters; the rows were grouped by month; and

_____

<img width="1440" alt="Screen Shot 2022-09-18 at 10 19 50 AM" src="https://user-images.githubusercontent.com/80941606/190911876-211ad7ac-f900-43d7-ba20-2aa0c2f04fa8.png">

**Image 2.0**: PivotTable for the theater outcomes by launch date.
_____

* Creating a PivotChart - line chart with markers - from the PivotTable.

_____

![theater_outcomes_vs_launch](https://user-images.githubusercontent.com/80941606/190911906-ffc2ae09-d109-4ffc-ba8a-341d0692c26e.png)

**Graph 1.0**: Theater campaign outcomes versus launch date of campaigns. 
_____

### Analysis of Outcomes Based on Goals
This analysis was conducted by:
* Creating an "outcomes_based_on_goals" worksheet with the following columns: campaign "goal" ranges, "number_successful", "number_failed", "number_cancelled", "total_projects", "percentage_successful", "percentage_failed", and "percentage_cancelled";
* Using the COUNTIFS function to count the number of successful, failed, cancelled campaigns;

_____

<img width="721" alt="Screen Shot 2022-09-18 at 10 25 22 AM" src="https://user-images.githubusercontent.com/80941606/190912026-0366a8fa-3ac4-48d8-a29f-e5b1eb57aa8e.png">

**Image 3.0**: An example of the COUNTIFS functions implementation.
_____

* Calculating the percentage of the number of successful, failed, cancelled campaigns; and

_____

<img width="1440" alt="Screen Shot 2022-09-18 at 10 20 56 AM" src="https://user-images.githubusercontent.com/80941606/190911939-094cc6e3-07ae-47cc-b260-42c7b3f2ab18.png">

**Image 4.0**: Data table for campaign outcomes based on campaign funding goal ranges.
_____

* Creating a line chart with markers to display the percentage of the number of successful, failed, cancelled campaigns based on campaign goal ranges.

_____

![outcomes_vs_goals](https://user-images.githubusercontent.com/80941606/190911923-b1f5e50a-6d7a-4acc-90bd-37e1aafb6034.png)

**Graph 2.0**: Theater play campaign outcomes versus campaign funding goals ranges.
_____

### Challenges and Difficulties Encountered
Many challanges were encountered and solved as described below:
* For the "theater_outcomes_by_launch_dates" PivotTable, the raw data needed to be modified so that the appropriate data could be used in the PivotTable (e.g. "date_created_conversion" and "years" columns were created). Additionally, grouping the row labels (i.e. "date_created_conversion") by months required the use of the esoteric "Group" function to achieve, which is a function that I was not familiar with until recently. 
* For the "outcomes_based_on_goals" table, the COUNTIFS function could not be copied from one column to another without changing the columns that were referenced in the formula in the "kickerstarter" sheet; although there are methods of preventing cell references from changing when coping and pasting formulas into new columns, I had manually modify the formulas to contain the correct cell references for new columns due to time constraints. Additionally, creating the chart required me to modify the data range selection from what is selected by default from excel in order to achieve Graph 2.0 above.

## Results

### Conclusions from Graph 1.0
* Two conclusions that I can draw about the outcomes based on launch date are that theater campaigns are most likely to succeed if they are launched in the middle of year and theater campaigns that are launched near the beginning/end of a year have similar probabilities of succeeding as they do of failing.

### Conclusions from Graph 2.0
* Two conclusions that I can draw about campaign outcomes based on funding goals is that the most successful theater play campaigns have funding goals that are less than $1,000 or between $35,000 and $40,000, and theater play campaigns are more likely to fail than succeed if the funding goals are between $15,000 to $35,000 or between $40,000 and $50,000.

### Limitations
* A limitation of this dataset is that there are only 4114 rows of data, a subset - 1393 rows - of which were used for the theater campaigns analysis; consequently, it is not a large enough sample size of data to arrive at any definitive conclusions. Additionally, this dataset may be outdated in 2022 since its data was collected many years ago.

### Future Analysis
* Some other possible tables and/or graphs that can be created are theater outcomes based on country, duration of the campaigns, staff picks, and spotlight.
