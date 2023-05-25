## The Scenario
Thinkful Qualified Data Querying and Manipulation in SQL

I am hired as a researcher for my state's department of education. I'm given a database containing two tables: naep and finance. NAEP is the National Assessment of Educational Progress for states. The naep table contains each state's average NAEP scores in math and reading for students in grades four and eight. The data spans various years between 1992 and 2017. The finance table contains each state's total K-12 education revenue and expenditures for the years 1992-2016.

I am tasked with assessing the quality of this data. I must also find useful ways to analyze it.

## #1
Begin analysis with the naep table. It's always a good idea to get a better understanding of the data before doing any analysis.

This allows me to gather key insights before I jump into any complex operations. I’ll want to know what columns are reported in the data and what the data types are for each column.

"Write a query that selects column_name and data_type from information_schema.columns."

<img width="458" alt="1" src="https://github.com/romaoeh/depedu_sql/assets/131217181/95d67fd4-d756-4100-9ab8-9ec2e65c045b">

## #2
"Write a query to select the first fifty records of the naep table."

<img width="463" alt="2" src="https://github.com/romaoeh/depedu_sql/assets/131217181/bfe09e8b-82e1-441c-83e2-92ee2567b0ed">


## #3
Another good way to understand the data is to calculate various summary statistics.

Summary statistics can give you very useful information, such as where your data is centered and how spread out it is. These summary statistics include count, average, min, and max values.

"Write a query that returns summary statistics for avg_math_4_score by state. Do this by using aliases, such as COUNT(avg_math_4_score) as count_4, and repeat this for the remaining aliases avg_4, min_4, and max_4, for AVG, MIN, and MAX, respectively. Finally, sort the results alphabetically by state name."

<img width="502" alt="3" src="https://github.com/romaoeh/depedu_sql/assets/131217181/3d29e560-42e8-44ad-ad60-40b5a8a756e4">

## #4
When a state has a large gap between the max and min values for a score, that's a good indicator that there may be problems with the education system in that state.

I decide that for avg_math_4_score, a gap of more than 30 between max and min values is probably a bad sign.

"Write a query that alters the previous query so that it returns only the summary statistics for avg_math_4_score by state with differences in max and min values that are greater than 30."

<img width="499" alt="4" src="https://github.com/romaoeh/depedu_sql/assets/131217181/cccccc8c-47f3-4d41-896f-131b20783b2d">

## #5
Now that I've gathered key insights about the data, I'm ready to do some analysis!

I want to report the 10 lowest-performing states for avg_math_4_score in the year 2000.

"Write a query that returns the avg_math_4_score as the alias avg_score and the state as the alias bottom_10_states that lists the states in the bottom 10 for avg_math_4_score in the year 2000."

<img width="497" alt="5" src="https://github.com/romaoeh/depedu_sql/assets/131217181/42484d2a-e9a8-4998-9221-ae73a1d26c6e">

## #6
"Write a query that calculates the average avg_math_4_score rounded to the nearest 2 decimal places over all states in the year 2000. The resulting variable should still be named avg_math_4_score."

<img width="501" alt="6" src="https://github.com/romaoeh/depedu_sql/assets/131217181/b492288e-577a-48c5-bc9e-791542657972">

## #7
"Write a query that returns a field called below_250 that lists all states with an avg_math_4_score less than 250, over all states in the year 2000."

<img width="499" alt="7" src="https://github.com/romaoeh/depedu_sql/assets/131217181/072f56d3-8ace-41f5-ad9f-070cf0df6b50">

## #8
In this exercise, I'll look at how to identify missing values. It's important to remember that if missing values are not handled properly, I may end up with inaccurate calculations and incorrect conclusions.

"Write a query that returns a field called scores_missing_y2000 that lists any states with missing values in the avg_math_4_score column of the naep data table for the year 2000."

<img width="500" alt="8" src="https://github.com/romaoeh/depedu_sql/assets/131217181/7469dc85-d35d-4ee1-a657-6dd7c1bb3326">

## #9
For this challenge, I'm being asked to display the average math score alongside the total expenditure to see if there is any relationship between the two. I am not focusing on doing correlations in this challenge; rather, this challenge will test my skills with using JOIN.

To accomplish my task, "write a query that returns, for the year 2000, the state, avg_math_4_score, and total_expenditure fields from the naep table left outer joined on the finance table, using id as the key and ordered by total_expenditure, from largest to smallest."

Be sure to round avg_math_4_score to the nearest 2 decimal places, keeping the variable name as is using an alias, and then filter out NULL from avg_math_4_scores in order to see the results more clearly.

<img width="501" alt="9" src="https://github.com/romaoeh/depedu_sql/assets/131217181/db691dd0-f6b4-436a-a9d8-086635147068">

