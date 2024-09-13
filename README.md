I'd like to walk you through how I basicly explore data.
First of all, when I have first glance at a new file of data, I will want to see how the data was formed and all the column names.
I used aggression functions such as MIN, MAX, SUM to see how it worked and ofc using ORDER BY to have a comprehensive view.
I created a column 'year-month' to see how many people was laid off at the particular time, using SUBSTRING and made sure the Month column IS NOT NULL.
Then I want to see over time how many ppl being laid off, so I created a CTE named Rolling_total calculated the total layoffs in each month, then go to my main query calculated a rolling total (cumulative sum) of layoffs.
At the final query, I want to rank between the companies so that I could learn top 5 has the highest number of layoffs for each year.
I created a CTE named Company_year have 3 column names, I used this first CTE as the reference table for the 2nd CTE, added 01 more column used DENSE_RANK, rank the company within each year, based on their total layoffs.
The last step is that I queried all data from the 2nd CTE with a filter.
