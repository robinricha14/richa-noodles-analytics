# Power BI Report Guide — NoodlesCrypto Top Performers & Analysis

## Overview
This report provides a multi‑page analytical dashboard for monitoring cryptocurrency engagement trends across Twitter and Reddit. It is built using MySQL (noodles_dw), ODBC connectivity, and Power BI Desktop. The report includes executive KPIs, time‑series trends, platform comparisons, and detailed currency drill‑downs.

The report contains
- 4 pages
- 12–15 visuals
- 8–12 DAX measures
- Interactive slicers, drill‑through, and parameters
- Load time  5 seconds (local MySQL)

---

## Data Model

### Tables & Views Loaded
- DimDate
- DimCurrency
- DimPlatform
- vw_ExecutiveDashboard
- vw_TimeSeries
- vw_SocialAnalytics
- vw_PlatformDaily

### Relationships (1 Single Direction)
 From (Dimension)  To (View)  Column 
-------------------------------------
 DimCurrency  vw_ExecutiveDashboard  Symbol → CurrencySymbol 
 DimCurrency  vw_SocialAnalytics  Symbol → Symbol 
 DimPlatform  vw_SocialAnalytics  PlatformName → PlatformName 
 DimDate  vw_TimeSeries  FullDate → FullDate 
 DimDate  vw_PlatformDaily  FullDate → FullDate 
 DimPlatform  vw_PlatformDaily  PlatformName → PlatformName 

### Date Table
DimDate is marked as the official date table using FullDate.

---

# Page 1 — Executive Dashboard

## Purpose
A high‑level overview of token engagement, quality, and social activity.

## Visuals
### 1. Top Tokens Table
Source vw_ExecutiveDashboard  
Columns
- CurrencySymbol  
- CurrencyName  
- TotalEngagements  
- AvgEngagementScore  
- TotalLikes  
- TotalComments  
- TotalRetweets  

Formatting
- Sort by TotalEngagements (Descending)  
- Conditional formatting on AvgEngagementScore (Green → Red)

### 2. Engagement Volume (Clustered Bar Chart)
- Y-axis CurrencySymbol  
- X-axis TotalEngagements  
- Filter Top N (parameter-driven)

### 3. KPI Cards
- Total Engagements  
- Avg Engagement Score  
- Distinct Currency Count  

### 4. Date Slicer (Synced Across All Pages)
- Field DimDate[FullDate]  
- Type Between  

---

# Page 2 — Time Series Analysis

## Purpose
Identify trends, spikes, and engagement patterns over time.

## Visuals
### 1. Engagement Over Time (Line Chart)
- X-axis FullDate  
- Y-axis TotalEngagements  
- Tooltip TotalPosts, ActiveCurrencies, AvgEngagementScore  

### 2. Social Activity Volume (Area Chart)
- X-axis FullDate  
- Y-axis TotalPosts  

### 3. Engagement Composition (Stacked Column Chart)
- X-axis FullDate  
- Values TotalLikes, TotalComments, TotalRetweets  

---

# Page 3 — Platform Analysis

## Purpose
Compare Twitter vs Reddit engagement and quality.

## Visuals
### 1. Platform Table
Source vw_SocialAnalytics  
Columns
- PlatformName  
- TotalEngagements  
- TotalLikes  
- TotalRetweets  
- AvgEngagementScore  
- LastEngagement  

### 2. Platform Comparison (Clustered Bar Chart)
- X-axis PlatformName  
- Y-axis TotalEngagements  

### 3. Engagement Quality (Column Chart)
- X-axis PlatformName  
- Y-axis AvgEngagementScore  

---

# Page 4 — Currency Deep Dive

## Purpose
Detailed analysis of a selected token across time and platforms.

## Visuals
### 1. Currency Selector (Slicer)
- Field DimCurrency[Symbol]

### 2. Engagement Trend (Line Chart)
- X-axis FullDate  
- Y-axis TotalEngagements  

### 3. Platform Split (Donut Chart)
- Legend PlatformName  
- Values TotalEngagements  

### Drill‑Through
From Executive Dashboard → Currency Deep Dive  
Field CurrencySymbol  

---

# Report-Level Features

## Date Range Slicer (Mandatory)
- Synced across all pages  
- Controls all visuals  

## Top N Parameter (Recommended)
- Name Top N Count  
- Used in Page 1 bar chart  

## Conditional Formatting
- AvgEngagementScore Green → Yellow → Red  
- TotalEngagements Light → Dark scale  

## Theme & Styling
- Theme Executive  Corporate  
- Font Segoe UI  
- Numbers right-aligned  
- Titles bold, 14pt  

---

# Submission Checklist
- PBIX saved under reportsNoodlesCrypto_TopPerformers.pbix
- Screenshots saved under reportsscreenshots
- 4 pages with 12–15 visuals
- 8–12 DAX measures created
- Date slicer synced across pages
- Drill-through working
- No visual errors
- Load time  5 seconds
