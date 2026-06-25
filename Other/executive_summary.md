# Executive Summary — Operational Performance & Lead Conversion Dashboard

## Business Context
A service organization needed a reliable view of CRM lead performance. The raw dataset contained duplicate lead IDs, inconsistent status labels, mixed date formats, inconsistent response-time units, city typos, and invalid interaction values.

## Objective
Build an Excel-only workflow to clean the data, create an analysis-ready dataset, and design an interactive dashboard that helps stakeholders monitor lead conversion, engagement, response speed, and operational performance.

## Method
1. Profiled 2,999 raw lead records.
2. Standardized IDs, client names, cities, statuses, dates, response times, and interaction counts.
3. Resolved duplicate leads using the latest lead date.
4. Built `tbl_CleanLeads` as the dashboard source.
5. Created PivotTables, KPI formulas, and an interactive Excel dashboard.

## Data Cleaning Summary
- **Raw records reviewed:** 2,999
- **Final unique leads:** 2,550
- **Duplicate Lead_ID rows resolved:** 449
- **Status variants standardized:** 23 variants reduced to 5 categories
- **Date formats standardized:** Multiple formats converted to standard Excel dates
- **Response time standardized:** Mixed units converted to hours

## Dashboards
1.  [[Dashboard_screenshot.png]]

## Portfolio Value
This project demonstrates data cleaning, quality control, feature engineering, PivotTable analysis, KPI design, dashboard development, and business communication using Microsoft Excel only.