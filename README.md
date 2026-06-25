# Project A - Operational Performance & Lead Conversion Dashboard
## Overview
In Company sales operations, data integrity is the foundation of strategic decision-making. This project showcases an end-to-end data cleaning and business intelligence solution built entirely within Microsoft Excel. By processing a raw, compromised CRM dataset of 2,999 records, I developed a completed, formula-based pipeline to resolve critical data quality issues, including duplicate ID, typos, inconsistent date formats, and irregular interaction counts. This resulting clean, reliable dataset enables accurate KPI tracking and actionable dashboard insights.
## Business Problem
A company was struggling to manage its CRM leads. Because the data was entered manually across multiple touchpoints, the raw export was heavily compromised by operational errors. Duplicate lead IDs skewed volume metrics, 23 different status variants fragmented the sales funnel, and mixed date formats prevented chronological trend analysis. Furthermore, response times were recorded in varying units (such as days, hours, and text strings), and interaction counts contained negative values and invalid text.

The goal was to clean everything in Excel and build a dashboard that helps answer:
- Which leads are converting?
- Which agents are performing well?
- Are response times too slow?
- Is engagement reaching the target level?
## The APPASA Framework
To ensure a structured and reproducible workflow, the project was executed using the five-stage APPASA method:

- **Assess:** I began by profiling the raw dataset to identify structural anomalies, missing values, and formatting inconsistencies across all ten columns.
- **Prepare:** I established a secure project environment, backing up the raw data and setting up dedicated mapping sheets to handle complex text replacements.
- **Process:** Using advanced Excel formulas, I engineered a cleaning pipeline that standardized text, parsed dates, and resolved duplicates without relying on external scripting or Power Query.
- **Study:** I built a series of structured PivotTables to analyze lead distribution, conversion rates, and agent response speeds.
- **Act:** Finally, I translated these analytical findings into an interactive executive dashboard and documented the entire transformation process for long-term maintenance
## Tools Used
I built this entirely in Microsoft Excel using Tables, formulas, PivotTables, charts, data validation, and conditional formatting.
## Skills Demonstrated
I demonstrated proficiency in Excel by cleaning raw CRM data and automating workflows through complex formulas. My process included ensuring data integrity, applying conditional formatting, and performing in-depth analysis using PivotTables. Additionally, I designed actionable KPIs and interactive dashboards to translate technical findings into clear, professional business reports.
## Cleaning Process
The cleaning process began by standardizing the unique lead identifiers and refining client names using a combination of `TRIM()` and `PROPER()` functions. Next, inconsistent city names were corrected using a dedicated mapping table, while raw status variants were consolidated into five standard pipeline stages: New, Contacted, Qualified, Converted, and Lost. Mixed date formats were then parsed into a single, uniform date column, response times were converted into hours, and interaction counts were cleaned to establish `Interaction_Count_Final` as the primary numeric metric. Finally, a strict duplicate-resolution rule was applied to keep only the latest record for each lead ID, followed by a thorough verification check to ensure the final table was completely ready for analysis.
## Dashboard Features
The interactive dashboard provides a comprehensive view of sales performance through the following features:

*   **KPI Cards:** Tracks Total Leads, Engagement Rate, Conversion Rate, Avg Response Time, and Total Target Sales.
*   **Visualizations:** Includes funnel and trend charts for performance tracking.
*   **Granular Analysis:** Offers breakdowns by agent, city, segment, and status.
*   **Interactivity:** Features slicers and timeline filters for dynamic data exploration.
*   **Design:** Utilizes a clean, intuitive layout optimized for quick executive review.
## Key Insights
*   **Data Reliability:** Standardized Excel processes replaced unreliable raw data, ensuring accurate reporting.
*   **Response Speed:** Leads contacted within 6 hours convert at higher rates.
*   **Engagement:** Success is tied to 3+ interactions.
*   **Strategic Targeting:** 70% of sales value comes from specific cities and segments.
*   **Pipeline Visibility:** The new dashboard provides clear, actionable tracking of lead health, agent performance, and opportunities.
## Project Files
- `data/raw/Raw_CRM_Leads_HERE.csv`
- `data/cleaned/crm_leads_cleaned_analysis_ready.csv`
- `workbook/Lead_Conversion_Dashboard.xlsx`
- `docs/cleaning_log.md`
- `docs/data_dictionary.md`
- `docs/executive_summary.md`
- `images/dashboard_screenshots/full_dashboard.png`
- `images/before_after_comparison.png`
## Screenshots
- - Raw data sample [https://github.com/mHarith2001/Project-A-Operation-Performance-Dashboard/blob/9196e95d29d4a4c4d00a023296c90dab4cadeaa0/Screenshot/Raw%20Dataset.png]
- Cleaning steps 
- QA checks
- Final dashboard ![full_dashboard](https://github.com/mHarith2001/Project-A-Operation-Performance-Dashboard/blob/9196e95d29d4a4c4d00a023296c90dab4cadeaa0/Screenshot/dashboard_screenshot/full_dashboard.png)
## How to Open the Workbook
- Open `Lead_Conversion_Dashboard.xlsx` in Microsoft Excel
- Review `Raw_Data`, `Clean_Data`, `Dashboard_Calcs`, and `Dashboard`
- Check the dashboard slicers and KPI cards
- Use the clean CSV export if you want a static dataset
## Contact
This project is part of my professional data analytics portfolio. If you have any questions, feedback, or opportunities, please feel free to reach out:

- **Name:** Muhammad Harith Bin Jamal
- **Role Focus:** Junior Data Analyst / Business Intelligence 
- **Certifications:** Google Data Analytics Professional, Macquarie University Excel Skills for Business
- **GitHub:** [[GitHub Profile](https://github.com/mHarith2001)]
- **LinkedIn:** [www.linkedin.com/in/muhammad-harith-4376332a0]
