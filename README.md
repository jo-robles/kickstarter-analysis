# Kickstarting with Excel - Module 1 Challenge
# Joel Robles

## Overview and Purpose of Project
The client (Louise) had recently made a determination to fundraise a project uitilizing data from past Kickstarter campaigns held from 2009-2017. Now, considering this success, Louise is wanting compartive data on how other campaigns fared in relation to their launch dates and funding goals. 

The purpose of doing this analysis was to take the initial Kickstarter dataset and perform an analysis to answer Louise's question. 

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date

The analysis began by taking the initial Kickstarter dataset and adding a column to identify the "Year" that a Kickstarter campagin launched. By accomplishing this, the data could be segmented out and filtered more efficiently.

After this step was completed, a pivot table was created to organize the data in a logical manner and a filter was added to only account for Kickstarter campaigns that fell under the Parent Category of "theater". Doing so allowed for the comparison that Louise requested to be similar to the campaign she had launched.

From there, utilizing the pivot table, a line chart visualizes the outcome of a theater kickstarter by month and the number of successful, failed and canceled outcomes:

https://github.com/jo-robles/kickstarter-analysis/blob/781eb1eea464f4c3d13a2411cb721d758d5f578f/Resources/Outcomes_vs_Goals.png

### Analysis of Outcomes Based on Goals

The analysis began by creating a table from the Kickstarter dataset that focused on the outcomes of the projects and their percentages of how successful (or unsuccessful) they were. Utilizing a COUNTIFS() formula such as:

=COUNTIFS(Kickstarter!$D:$D,">19999",Kickstarter!$D:$D,"<25000",Kickstarter!$F:$F,"=failed",Kickstarter!$R:$R,"=plays")

Data was pulled from the master Kickstarter dataset and, utilizing specific crtieria, was filtered out to the data table. From there, simple arithmetic was utilized to gather percentages to create an understanding of the percentage of successful (or unsuccessful) campaigns based on a range of goals for the Kickstarter campaigns. 

After these percentages were calculated, a line chart was created to present the data:

INSERT LINK HERE

### Challenges and Difficulties Encountered

No challeges were observed in creating the pivot table or line chart for the "Analysis of Outcomes Based on Launch Date". However, one challenge or limitation that can be observed is that there are projects that are currently "live" which are not accounted for within the final line chart. Therefore, by not being mindful of this (and not filtering this data out), it is possible to create a table with more information than is necessary for the analysis.

For the "Analysis of Outcomes Based on Goals", a primary challenge that was observed was setting forth the appropriate criteria (e.g., > or <) for goals in writing the =COUNTIFS formula. In order to overcome these challenges, three approaches were utilized: writing out the intent of the formula, reading documentation from Microsoft on how the =COUNTIFS formula is supposed to work, and utilizing simple a =COUNTIFS to error check.

To elaborate on these methods individually, the first method involved writing in plain english what the formula was supposed to do. So, in this case =COUNTIFS(Kickstarter!$D:$D,"<1000",Kickstarter!$F:$F,"=successful",Kickstarter!$R:$R,"=plays"), the formula is written like this: The intent of this formula is to count data that meets the following criteria: Column D in the Kickstarter sheet of the spreadsheet any values that are less than 1000, Column F that contains the text - successful and Column R that contains the text - play. By doing so, it was easier to identify potential issues in the forumla that may exist.

The second method utilized was reading the documentation that Microsoft provided on the =COUNTIFS formula. Doing so enabled a deeper understanding of the syntax that was necessary to be utilized by Microsoft Excel to make sure the formula worked.

The final method utilized was taking error checking by taking the sum total of "successful" outcomes in the Kickstarter campaigns (utilizing the following forumla on the Kickstarter sheet - "=COUNTIFS(F:F,"=successful) after filtering by the "play" subcategory. This number was compared agains the "Total Projects" column value to ensure that these two numbers matched. In cases where they didn't, further scrutiny was utilized to determine if errors were made via typos.  

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

1) When considering launching "Theater" Kickstarter campaigns, May seems to be a great month to do so. 
2) Similarly, when considering launching "Theater" Kickstarter campaings, December might be the worst month to do so. 

- What can you conclude about the Outcomes based on Goals?

1) With consideration to the data present, Kickstarter campaigns tend to have lower rates of success as their overall funding goals increase with a large increase in failure rates as goals rise above $45000. However, there seems to be be an exception with goals set at $35000 to $44999 and further analysis would likely be warranted to determine the exact cause behind this. 

- What are some limitations of this dataset?

1) The analysis performed does not take into account those Kickstarter campaigns that are still categorized as "live". With that in mind, some of the analysis is incomplete.
2) The dataset included multiple countries and, as a result, some of the analysis may not be comparable when considering the location of Louise's needs. 
3) The dataset is older when considering the current year - 2021 and additionally, when considering the full scope of years (since 2009), relevance would be an issue. 

- What are some other possible tables and/or graphs that we could create?

2 come to mind readily:

1) Average Donation by launch date

This could provide some insight into how much an individual could reasonably ask for when considering soliciting indivdiual donations to achieve a favorable result.

2) Average Number of Backers by Outcome

This could provide some insight into the number of backers to be targeted by campaigns as they launch Kickstarters. 
