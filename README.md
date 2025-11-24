# SALES OPPORTUNITY ANALYTICS

## 📌 Table of Contents
- [1. Project Overview](#1-project-overview)
- [2. Business Problem](#2-business-problem)
- [3. Data Sources](#3-data-sources)
- [4. Data Cleaning & Transformation (Power Query)](#4-data-cleaning--transformation-power-query)
- [5. Data Modeling](#5-data-modeling)
- [6. DAX Measures Created](#6-dax-measures-created)
- [7. Dashboard Design & Visuals](#7-dashboard-design--visuals)
  - [Page 1: Overview Dashboard](#page-1-overview-dashboard)
  - [Page 2: Salesperson-details](#page-2-salesperson-details)
- [8. Key Insights From the Dashboard](#8-key-insights-from-the-dashboard)
- [9. Tools Used](#9-tools-used)
- [10. Project Deliverables](#10-project-deliverables)
- [11. Potential Extensions](#11-potential-extensions)

---

## 1. Project Overview

This project focuses on analyzing sales opportunities across multiple countries, channels, and sales stages using an interactive Power BI dashboard. The goal was to transform raw Excel data into a clear, insight-driven reporting tool that helps business leaders understand pipeline health, team performance, and revenue contribution.

The report contains two main pages:

**Overview Dashboard** – a high-level summary of opportunities, value, win rates, channels, countries, and top-performing salespeople.

**Salesperson Details Page** – a drill-down view showing each salesperson’s activities, metrics, and complete opportunity history.

This dashboard supports data-driven decision-making by summarizing performance trends and highlighting areas that need managerial attention.

---

## 2. Business Problem

The organization relies on multiple sales channels and a team of salespeople operating across different regions. However, tracking opportunities, understanding deal progress, and assessing team performance is difficult due to scattered spreadsheets and inconsistent data formats. This affects leadership’s ability to monitor pipeline strength, identify bottlenecks, evaluate salesperson effectiveness, and forecast revenue accurately. A centralized dashboard is needed to transform the raw data into actionable insights that support better strategic and operational decisions.

---

## 3. Data Sources

The dataset consisted of two Excel worksheets:

**Worksheet 1: Sales Details**
- Opportunity ID  
- Reporting Date  
- Salesperson  
- Customer  
- Country  
- Sales Stage  
- Opportunity Value (USD)  
- Sales Channel (Telesales, Website, F2F, Partners)  
- Close Date  
- Next Step  

**Worksheet 2: Salespersons**
- Salesperson  
- Profile Image  

These two sheets were imported into Power BI for transformation, modeling, and report development.

---

## 4. Data Cleaning & Transformation (Power Query)

**Steps Completed:**

1. Loaded both worksheets into Power BI.  
2. Checked for and handled blanks, nulls, and incorrect entries.  
3. Standardized inconsistent entries, including:
   - “UK” → “United Kingdom”
   - “US” → “United States”
4. Verified and corrected data types, ensuring dates, text, numbers, and currencies were properly assigned.  
5. Checked for spelling errors and column name inconsistencies and corrected them.  
6. Merged the datasets on the Salesperson field to attach the profile images to each record.  
7. Reformatted all date fields to dd-mm-yyyy.  
8. Created a full Date Table with:
   - Date  
   - Year  
   - Month Number  
   - Month Initials  
9. Established relationships between the Date Table and the Sales Details table using Reporting Date.

These steps ensured a clean, accurate, and analysis-ready dataset.

---

## 5. Data Modeling

A star schema model was developed:

### Fact Table
- Sales Opportunities (all transactional opportunity data)

### Dimension Tables
- Date Table  
- Salesperson Table (with image)  
- Country (implicit)  
- Sales Channel (implicit)

This structure made the model efficient, scalable, and suitable for DAX calculations.

---

## 6. DAX Measures Created

To support analysis, several measures were created:

### Opportunity Counts
- Total Opportunities  
- Won Opportunities  
- Lost Opportunities  

### Opportunity Values
- Total Opportunity Value  
- Opportunity Value Won  
- Opportunity Value Lost  

### Performance Metrics
- Win Rate  
- Conversion Rate  

### Calculated Column
**Deal Status:**
- “Won” if Sales Stage = Won  
- “Lost” if Sales Stage = Lost  
- “Open” for all other stages  

These measures powered KPI cards, charts, and tables across the dashboard.

---

## 7. Dashboard Design & Visuals

### Page 1: Overview Dashboard

This page provides a full performance snapshot and includes:
- KPI Cards for Opportunities, Won, Lost, and Opportunity Value  
- Line Charts for monthly trends  
- Win Rate and Conversion Rate gauges  
- Sales Pipeline Funnel showing each stage (Validated → Proposal → Won/Lost)  
- Opportunities by Sales Channel (donut chart)  
- Opportunities by Country (filled map)  
- Top 5 Salespersons Table with:
  - Photo  
  - Opportunity Value  
  - Number of Opportunities
  
<img width="1034" height="560" alt="Sales Opportunity" src="https://github.com/user-attachments/assets/9e80522c-5401-4052-b229-5a19ed577d28" />

### Page 2: Salesperson-details

A profile-level report containing:
- Salesperson photo  
- Total Opportunities handled  
- Total Opportunity Value  
- Win Rate  
- Complete opportunity list (with stage, value, channel, country, and dates)

Filters for:
- Year  
- Month  
- Country  

This page helps managers evaluate individual performance.

<img width="985" height="562" alt="Salesperson Details" src="https://github.com/user-attachments/assets/7c4ebe8c-3318-4da3-840c-59f431d8752a" />

---

## 8. Key Insights From the Dashboard

- Telesales generated the highest proportion of opportunities.  
- The pipeline shows a major drop-off at the Proposal stage, indicating negotiation challenges.  
- High-value opportunities are concentrated in countries like the US, Germany, China, and Australia.  
- Top performers such as Angela Chen and Tim Parker drive a significant share of opportunity value.  
- Win Rate stands at 80%, while Conversion Rate is 27%, showing room for improvement.

---

## 9. Tools Used

- Microsoft Power BI  
- Power Query Editor  
- DAX (Data Analysis Expressions)  
- Excel  

---

## 10. Project Deliverables

- Fully interactive 2-page Power BI report  
- Clean and structured dataset  
- Star schema data model  
- Reusable DAX measures  
- Text documentation for portfolio use  

---

## 11. Potential Extensions

- Add salesperson targets for performance comparison  
- Implement revenue forecasting using DAX  
- Introduce deal aging metrics  
- Schedule automatic data refresh via Power BI Service  
- Add row-level security for sales teams  
- Connect to a live CRM system (HubSpot / Salesforce)
