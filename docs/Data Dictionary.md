# Data Dictionary - Clean CRM Leads

## Dataset Overview
- **Source table:** `tbl_CleanLeads`
- **Workbook sheet:** `Clean_Data`
- **CSV export:** `data/cleaned/crm_leads_cleaned_analysis_ready.csv`
- **Rows:** 2,550
- **Duplicate lead IDs:** 0
- **Export date:** 2026-06-22

## Field Definitions
- **Assigned_Agent:** Sales or service agent assigned to the lead.
- **Lead_ID_Fixed:** Standardized unique lead identifier.
- **Client_Name_Fixed:** Cleaned client name using trim and proper-case logic.
- **Company_Segment:** Customer or company segment classification.
- **City_Final:** Standardized city name after mapping corrections.
- **Status_Clean:** Standardized pipeline status.
- **Lead_Date_Final:** Cleaned lead entry date.
- **Lead_Month_No:** Numeric month value used for sorting.
- **Lead_Month:** Month name used in dashboard labels.
- **Lead_Year:** Calendar year.
- **Lead_Quarter:** Calendar quarter label.
- **Lead_Weekday_No:** Numeric weekday value used for sorting.
- **Lead_Weekday:** Weekday name.
- **Response_Time_Hours:** Response time converted to hours.
- **Target_Sales:** Forward-looking quota or potential value.
- **Interaction_Count_Final:** Cleaned total interaction count.
- **Sales_Tier:** Low, Medium, or High tier based on target-sales percentiles.
- **Is_Converted:** Binary conversion flag where `1` means Converted.
- **Is_Engaged:** Binary engagement flag where `1` means Contacted, Qualified, or Converted.
- **Stage_Order:** Numeric order for funnel-stage sorting.
- **Response_Speed_Cat:** Response-speed category used for SLA-style review.
- **Response_Bucket_6H:** Response-time bucket based on a 6-hour threshold.
- **Engagement_Level:** Engagement category based on interaction depth.

## Usage Notes
- **Target_Sales** is a quota or potential value, not actual revenue. Do not use it for financial reporting or commission calculations.
- The dataset is deduplicated by `Lead_ID_Fixed`, with the latest valid lead record retained.
- Invalid or unusual values were checked during cleaning so the final dataset can be used for dashboard analysis.
