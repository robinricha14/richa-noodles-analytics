# Executive Dashboard Guide – Noodles Crypto

## 1. Overview
This dashboard package is designed as an executive-style reporting experience for cryptocurrency engagement and market activity. It is based on the processed ETL outputs already available in this workspace and is structured to support stakeholder review and portfolio-style presentation.

## 2. Source Data
The report should be built from the following files:
- dim_currency.csv
- fact_supply.csv
- fact_social.csv

These datasets provide the foundation for token-level metrics, supply snapshots, and social engagement trends.

## 3. Proposed Report Pages

### Page 1 – Executive Overview
Purpose:
- Highlight top-performing tokens
- Display overall engagement and activity
- Present high-level KPI cards

Suggested visuals:
- KPI cards for total engagements, average engagement score, active tokens
- Trend line for engagement over time
- Top tokens table
- Platform engagement donut chart

### Page 2 – Platform Performance Analysis
Purpose:
- Compare platform activity across Twitter and Reddit
- Review engagement quality by platform

Suggested visuals:
- Trend line using a date axis
- Platform summary table
- Engagement score comparison chart

### Page 3 – Token Drill-Through
Purpose:
- Show detailed activity for a selected token
- Support interactive drilling from the executive overview

Suggested visuals:
- Token engagement trend chart
- Platform split chart
- Engagement breakdown table

## 4. Recommended Measures
The report should contain measures for:
- Total Engagements
- Average Engagement Score
- Total Likes
- Total Comments
- Total Retweets
- Engagement Growth %
- Engagements 7D Avg
- Platform Share %

## 5. Advanced Features to Include
- Slicers for date range and token
- Cross-filtering between visuals
- Drill-through for token analysis
- Bookmarks for overview and platform comparison views
- Consistent executive theme and formatting

## 6. Submission Notes
This workspace contains the documentation and structure needed for a polished submission. The Power BI Desktop file can be finalized in a local Power BI environment by importing the processed CSV files and applying the page design described above.
