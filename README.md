# Project 1 US Debt 

Questions:
1. What was the Yearly Debt Percentage Increase for each year compared to the previous year?
2. Which months historically have seen the highest/lowest increases in Total debt?
3. What is the projected growth of the publicly held debt in the next few years?

Data Dictionary	Definition
Debt Held by the Public	This is the portion of the US public debt that is held by individuals, corporations, foreign governments, and other entities outside of the US government.
Intragovernmental Holdings	This is the portion of the US public debt that is held by other US government agencies.
Total Public Debt Outstanding	This is the sum of the debt held by the public and intragovernmental holdings.

Using questions and data dictionary provided, answer questions using charts/graphs and narratives

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
