# Project 1 US Debt 
Questions:<br>
What was the Yearly Debt Percentage Increase for each year compared to the previous year?<br>
Which months historically have seen the highest/lowest increases in Total debt?<br>
What is the projected growth of the publicly held debt in the next few years?<br>

Steps:
1. Change layout - copy to Cleaned Data Sheet 
2. Copy/paste(transpose) make rows columns and columns rows (to 7495 rows)
3. Null data is null not 0 - was probably not tracked in those years; filter  (select data, Data ->Filter
4. Delete blanks Completely blank in all rows via filter if there are any blanks (none)
5. Select nulls (Col B Debt Held...) 2,959 nulls and it's text/string We want it numeric Clear filter and use  Ctrl H Find and replace (Find null replace blank then Replace All (5916 replacements) Will now have new blanks from this step
6. Change scientific notation: Select range Home change Scientific to Number Add comma Delete numbers after decimal point
7. New Sheet with question 1 and copy cleaned data and identify yearly debt We can see yearly debt at end of year (eg. 12/30/2022) So filter Col A Record Date by Dec last day of month for each year - go back ~ 10 years. Not full year data for 2023 ends at 2/15/2023 in dataset
8. calculate percentage increase from Col B Debt Held by the Public as":=(B2-B33)/B33*100 THEN =(B33-B283)/B283*100 ... for each filtered row
9. Apply to other two columns C Intragovernmental holdings D Total Public Debt Outstanding by dragging new column completed in step 8 (drag over 2 columns)
10. For better layout copy below data and add first column Year 
11. As this is time series, use line chart
12. On chart, years are not in order so highlight data from Step 10 and sort smallest to largest
13. Exclude 2023 data in chart filter as only 2 months of data
14. Add line chart in Final Outputs sheet
15. For question 2 copied cleaned data to new sheet. Need to identify months historically have seen the highest/lowest increases in Total debt
16. Aggregate data based on months by average by pivot table: Record Date in Row but only Months; Value is Average of Total Public Debt and change to number format with no decimals
17. Looking at aggregation will select clustered column pivot chart for 2nd visual
18. Third question projected growth forecasting function in Excel: based on max debt per year
19. Pivot table from 'Cleaned Data'!$A$1:$D$7496; Years(Record Date) for rows, Value is MAX of Debt Held by the Public
20. Copy/paste as value the rows 1993-2023 as numbers
21. Forecast will do =FORECAST.ETS(E34,$F$8:$F$33,$E$8:$E$33) starting at 2023
22. Can do for 2024-2027 need to drag down prior year's forecast and year in function
23. Logical but probably not as accurate as Python
24. Use that new data with forecast for stacked chart and copy in Final Output

# Project 2 NYC Bus Transportation

Questions:<br>
What are the most common reasons for delays and breakdowns?<br>
How do delay times vary by bus company and borough?<br>
Is there a correlation between specific days of the week and the frequency of breakdowns or delays?<br><br>
Steps:
1. Copy to new sheet for cleaning
2. Find weekday of Occurred_On column =Weekday(H2) and make column Number 1=Sunday 2=Monday...
3. Duplicate variations of bus company names Copy as values in another col Will aggregate to present on high level Example: use filter for Careful Bus and Careful Bus Service, Inc (B2192) Select the two Ctrl C on first cell, Ctrl Shift down, Paste 
4. Copy How_Long_Delayed Go to Data->Text to Columns Delimiter is - repeat on new col delimiter is space So instead of 46-60 Min it will be 40 in 1 col 60 in another col Min in another col
5. From filter confirm all in Min so deleted that col
6. Last_Updated_On has 1/1/1900 0:00 In filter select 1900 and delete
7. Look at common reason for delay: pivot table on Reason column Reason is Rows and Count of Reason is Value Also use Breakdown_or_Running as column in order to break it down by delay and reason in order to find most common Sort smallest to largest and filter Breakdowns
8. Add bar chart and select Breakdown to visualize reasons
9. Repeat step 7 and 8 but filter for Running late
10. Question 2- pivot table  Look at delay times by company and borough and sort largest to smallest
11. From cleaned data show filter Short and Long delay is blank and filter on Running Late (from Breakdown_or_Running) There's only 1 Add 0 Short/Long instead of blank
12. Pivot chart to see how delays vary by bus company
13. Due to size of data for better chart, value filter from Row Labels and do top 10
14. Another pivot chart with rows on Boro and sort small to largest
15. See there is (blank) in Boro In Cleaned Data Boro filter by blank Keep in data, remove from pivot filter
16. Question 3 Look for pattern between day of week and frequency(count)
17. Copy over previous pivot table to sheet 3 Rows Day_Of_Week and Legend Breakdown_or_Running_late and Count Breakdown_or_Running_Late as value
18. There is one outlier we will filter out in pivot filter
19. Create line chart
20. Copy paste table We will filter between Running Late for 1st and Breakdown for 2nd
21. Go back to cleaned data and make user friendly days of week in lieu of numbers
22. In tables select Mon-Fri and sort alphabetically

