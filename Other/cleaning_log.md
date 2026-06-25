# Data Cleaning Log for Project A Operation Performance
**Date:** 2026-06-16 | **Analyst:** [Muhammad Harith]
## 1. Profiling
- **Action:** On my cleaning process, I established a profiling sheet to serve as a foundational baseline before beginning the data cleaning process. In the process, I have used a formula to calculate the total volume per column. After that, I also verified the data structure to ensure accuracy.
- **Formula:** `=ROWS(Table1[Lead_ID])`
- **Result:** This provides a clear overview of the total volume per column and helps identify any immediate data errors. In result, this confirms the dataset size is ready for further processing.
- **Why:** The reason is that this initial profiling acts as the benchmark for all subsequent data transformations. This is why it is essential to establish a baseline on this stage of the project.
[[Pasted image 20260616114900.png]]
## 2: Lead_ID - Standardize Lead
**Action:** On my cleaning process, I standardized the `Lead_ID` values by applying `TRIM` and `UPPER` functions and prefixing them with "CL-". In the process, I have also implemented a duplicate flag to identify recurring entries. After that, I removed 449 duplicate `Lead_IDs`, deciding to keep only the first occurrence for unique lead analysis.
**Formula:** =IF(COUNTIF($A$2:A2, "CL-"&TRIM(UPPER(Table1[@[Lead_ID]])))>1, "Duplicate", "CL-"&TRIM(UPPER(Table1[@[Lead_ID]])))
**Result:** This generated a 3-column table containing the cleaned ID, the standardized format, and a duplicate status flag. In result, this ensures the dataset is free of redundant entries and ready for accurate analysis.
**Why:** The reason is that consistent formatting is required to maintain data integrity across the entire dataset. This is why I implemented the duplicate flag—to ensure reliable results for all downstream analysis.
[[Pasted image 20260616121616.png]]
## 3: Client_Name - Standardize Client
- **Action:** I have used the `PROPER` and `TRIM` tools to tidy up the client names. After that, I made a special column to keep the names looking the same and added underscores.
- **Formula:** =SUBSTITUTE(TRIM(PROPER([@[Client_Name]]))," ","_")
- **Result:** In result, the client names are now standard and easy to sort. Also, what I have done makes the list look very neat.
- **Why:** The reason is that the old list had messy spaces and letters. This is why I fixed it; as this, the data is now much better for my reports.
[[Pasted image 20260616121654.png|313]]
## 4: City - Standardize City Names
- **Action:** I have created a `City_Mapping` sheet to fix city names that were not written the same way. What I have done is take all the unique names, then I used `TRIM` and `PROPER` to make them look clean. After that, I manually matched the different versions to the right names. I also added `City_Clean` and `City_Final_Corrected` columns to my main file to help me fix things automatically.
- **Formula:** =IFERROR(VLOOKUP([@[City_Clean]],City_Mapping!A:B,2,FALSE),[@[City_Clean]])
- **Result:** In the process, I turned 68 different city names into one clear list. In result, all the names are now the same. As this, I can see that the data is much more organized.
- **Why:** The reason is that the old list had many spelling errors and mixed-up letters. This is why I had to clean it, so that my regional reports are correct.
[[Pasted image 20260616132450.png]]
## 5: Status - Standardize Statuses
- **Action:** I have created a `Status_Norm` column in my `Raw_Data` sheet. What I have done is use `TRIM` and `UPPER` to make the text look clean. Then, I made a `Status_Mapping` sheet to turn 23 messy versions into 5 standard statuses: `New`, `Contacted`, `Qualified`, `Converted`, and `Lost`. After that, I used `VLOOKUP` to fill the `Status_Final` column. I also added binary flags where `1` means a lead moved forward and `0` means it did not. Finally, I gave each stage a number from 1 to 5 to keep them in the right order.
- **Formula:** =IFERROR(VLOOKUP([@[Status_Norm]],Status_Mapping!D:E,2,FALSE),[@[Status_Norm]])
- **Result:** In the process, I fixed all the typos and capital letter mistakes. In result, I now have 5 clear categories. As this, I can easily calculate conversion and engagement rates using a PivotTable. Also, the funnel stages now stay in the correct business order.
- **Why:** The reason is that I need to track every status the same way for my reports. This is why I used numeric flags; they make my math much simpler. On this, I also used numbers for the stages because Excel likes to sort text by A-Z, but I need the funnel to follow the real sales steps.
[[Pasted image 20260616143256.png]]
[[Pasted image 20260622125107.png]]
[[Pasted image 20260622125415.png]]
## 6: Lead_Date - TitleofAction
- **Action:** I have fixed the `Lead_Date` column because it had five different date styles. What I have done is create a chain of helper columns on the `Raw_Data` sheet to change every date into a format Excel can read. Then, I changed dots and dashes into slashes. After that, I used a formula to check if the dates were correct. I also made a `Date_Final` column to keep only the good dates. I also created four new columns for `Lead_Month`, `Lead_Year`, `Lead_Quarter`, and `Lead_Weekday` to use in my charts. To remove duplicate records, I first added an `Original_Row_No` column. Then, I used `MAXIFS()` to find the newest date for each lead. After that, I marked the rows I wanted to remove, filtered them, and deleted them. Finally, I checked the list to make sure no duplicates were left.
- **Formula:** =LET(txt,TRIM([@Lead_Date]),
- **Result:** In the process, I turned all the messy dates into a clean list. In result, I have 2,999 valid dates that go from January 2023 to December 2024. As this, I can now use these dates in my dashboard and slicers without any errors.
- **Why:** The reason is that I need to show exactly how I fixed the data if someone asks. This is why I kept every step visible. On this, the validation check helps me find mistakes before they reach my final reports.
[[Pasted image 20260617190420.png|710]]
## 7: Response_Time - Standardize Response Time
- **Action:** I have created a mapping sheet to find different ways people wrote the response time, such as "h," "hrs," "hours," or "days." What I have done is set up a rule to change these into one standard format. Then, I added a `Response_Time_Hours` column in the `Raw_Data` sheet. I also created a `response_speed_cat` column to group the times together. After that, I used a formula to turn the text into numbers. This helps me understand how fast the team replies to customers.
- **Formula:** =IFS(ISNUMBER(SEARCH("h", [@[Response_Time]])), VALUE(LEFT([@[Response_Time]], LEN([@[Response_Time]])-1)), ...)
- **Result:** In the process, I changed all the different time notes into one clear number. In result, every entry is now in hours. As this, I can see the speed of the team very clearly.
- **Why:** The reason is that I need to compare the times in the same way to make my reports fair. This is why I changed everything to hours. On this, it also makes it much easier to track performance over time.
[[Pasted image 20260617084810.png|354]]
[[Pasted image 20260622124040.png]]
## 8: Interaction_Count - Standardize Interaction Count
- **Action:** I have standardized the interaction counts by making a new column called `Interaction_Count_Clean`. What I have done is use `LET` to remove extra spaces and `ABS` to turn negative numbers into positive ones. I also used `IFERROR` so that text like "N/A" stays the same. Then, I created an engagement column to label the interactions as low, mid, or high. After that, I checked the data to make sure it was ready.
- **Formula:** =LET(txt, TRIM([@Interaction_Count]), IFERROR(ABS(VALUE(txt)), txt))
- **Result:** In the process, I turned all the messy counts into clean numbers. In result, the negative numbers are now positive, and the "N/A" labels are still there. As this, the data is much more organized for my work.
- **Why:** The reason is that I need the numbers to be consistent for my charts and models. This is why I cleaned them up. On this, it also helps me keep the important text labels safe while I do my math.
 [[Pasted image 20260622123430.png]]
[[Pasted image 20260617104018.png|453]]
## 9: Target_Sales - Categorize Sales Tiers
- **Action:** I have identified and cleaned the numeric columns that had mixed text or symbols. What I have done is use the `ISNUMBER()` tool to find bad entries, then I used a formula to fix them. After that, I also created a `Sales_Tier` column. This helps me put `Target_Sales` into three groups: `Low`, `Medium`, and `High`. I did this by looking at the percentile of the numbers.
- **Formula:** `=IF(J2<=PERCENTILE.INC(Table1[Target_Sales],0.25),"Low",IF(J2<=PERCENTILE.INC(Table1[Target_Sales],0.75),"Medium","High"))`
- **Result:** In the process, I turned the raw numbers into clear groups. In result, I can now see which leads are the most valuable. As this, it is much simpler to decide which tasks to finish first.
- **Why:** The reason is that raw numbers are hard to read on their own. This is why I made these groups; it helps me track performance and use my time better. On this, it also makes my reports much more useful for planning.
[[Pasted image 20260617100111.png|503]]
## Data Validatation Rules
- I have applied data validation rules to the key fields in `tbl_CleanLeads`. What I have done is check `Status_Clean`, `Assigned_Agent`, `Response_Time_Hours`, `Interaction_Count_Final`, and `Lead_Date_Final`.
- Then, I made sure no one can enter wrong information. After that, I saved a screenshot as proof of my work.
- In the process, I also made sure the workbook is safe to use for future CRM exports. In result, the data will stay clean.
- The reason is to prevent invalid manual updates. This is why I added these rules; as this, the file stays reliable on this project.
 [[status_clean_data_validation.png]]
[[Response_Time_Hours_Data_Validation.png]]
[[Lead_Date_Final_Data_Validation.png]]
## Conditional Formatting
- I have applied conditional formatting to the `CleanLeads` table. What I have done is highlight duplicate `Lead_ID_Fixed` entries, high `Response_Time_Hours`, and missing `Interaction_Count_Final` values.
- Then, I also marked converted leads and any missing `City_Final` data. After that, I saved a screenshot as proof of my work.
- In the process, I made it much easier to see important records and data errors. In result, I can review the quality of the information visually.
- The reason is to spot mistakes quickly. This is why I used these colors; as this, I can keep the data clean on this project.
  [[conditional_formatting.png]]

## Insight Questions
- **Pipeline:** Analyze status distribution to identify which status holds the largest share of leads.
- **Conversion:** Determine which customer segment achieves the highest conversion rate.
- **Response Speed:** Evaluate the correlation between faster response times and improved conversion outcomes.
- **Agent Performance:** Compare agents to identify who handles the highest lead volume versus who achieves the best conversion results.
- **Geography:** Identify the top cities contributing the highest lead volume and total target value.
- **Engagement:** Assess whether a higher number of interactions is associated with better conversion rates.
- **Time Trend:** Track monthly trends to see if lead volume or response times are improving over time.
## Final QA
- **Rows after cleaning:** 2,550
- **Duplicate Lead_ID_Fixed:** 0
- **Date failures:** 0
- **Status unmapped:** 0
- **Formula errors:** 0
