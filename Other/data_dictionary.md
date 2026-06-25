# Data Dictionary: Clean CRM Leads

### Dataset Overview
- **Source:** `tbl_CleanLeads` (Sheet: `Clean_Data`)
- **Export:** `crm_leads_cleaned_analysis_ready.csv`
- **Rows:** 2,550 | **Duplicates:** 0
- **Export Date:** 2026-06-22

### Field Definitions
- **Lead_ID_Fixed:** Unique lead identifier.
- **Client_Name_Fixed:** Anonymized client name (cleaned via TRIM/PROPER).
- **Company_Segment:** Business segment classification.
- **City_Final:** Standardized city name.
- **Assigned_Agent:** Responsible sales or service agent.
- **Lead_Date_Final:** Standardized lead entry date.
- **Lead_Month_No / Lead_Month:** Month number and label.
- **Lead_Year:** Calendar year.
- **Lead_Quarter:** Q1–Q4 label.
- **Lead_Weekday_No / Lead_Weekday:** Weekday order and name.
- **Status_Clean:** Standardized pipeline status.
- **Response_Time_Hours:** Response time converted to hours.
- **Interaction_Count_Final:** Cleaned total interaction count.
- **Interaction_Flag:** Validity status for interaction data.
- **Target_Sales:** Forward-looking quota/potential value.
- **Sales_Tier:** Low/Medium/High segment based on percentiles.
- **Response_Speed_Cat:** SLA performance category.
- **Engagement_Level:** Categorization based on interaction depth.
- **Is_Converted:** Binary flag (1 = Converted).
- **Is_Engaged:** Binary flag (1 = Contacted, Qualified, or Converted).
- **Stage_Order:** Numerical sort order for funnel visualization.

### Important Usage Notes
- **Target_Sales:** This is a quota, not actual revenue. Do not use for financial reporting or commission calculations.
- **Data Integrity:** Dataset is deduplicated by `Lead_ID_Fixed` (latest record retained).
- **Metrics:** Invalid interaction counts are flagged to ensure accurate productivity reporting.