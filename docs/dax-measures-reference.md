# DAX Measures Reference

## 1. Executive KPI Measures
| Measure | Category | Purpose | Data Source | Formula |
|---|---|---|---|---|
| Total Engagements | KPI | Sum all engagement volume | fact_social.csv | SUM(FactSocial[EngagementValue]) |
| Average Engagement Score | KPI | Show average engagement quality | fact_social.csv | AVERAGE(FactSocial[EngagementScore]) |
| Total Likes | KPI | Show total likes across the selected scope | fact_social.csv | SUM(FactSocial[Likes]) |
| Total Comments | KPI | Show total comments across the selected scope | fact_social.csv | SUM(FactSocial[Comments]) |
| Total Retweets | KPI | Show total retweets across the selected scope | fact_social.csv | SUM(FactSocial[Retweets]) |

## 2. Time Intelligence Measures
| Measure | Category | Purpose | Data Source | Formula |
|---|---|---|---|---|
| Engagement Growth % | Time Intelligence | Compare current engagement with previous period | fact_social.csv | DIVIDE([Total Engagements] - [Previous Period Engagements], [Previous Period Engagements], 0) |
| Engagements 7D Avg | Time Intelligence | Show a short-term rolling average | fact_social.csv | AVERAGE([Total Engagements]) |

## 3. Ranking and Helper Measures
| Measure | Category | Purpose | Data Source | Formula |
|---|---|---|---|---|
| Token Engagement Rank | Ranking | Rank tokens by engagement | dim_currency.csv | RANKX(ALL(dim_currency[symbol]), [Total Engagements], , DESC, Dense) |
| Platform Share % | Helper | Show share of engagement by platform | fact_social.csv | DIVIDE([Total Engagements], CALCULATE([Total Engagements], ALL(FactSocial)), 0) |

## 4. Notes for Use
- Measures should be created in a dedicated measure table for clarity.
- Date-based measures should be tied to a proper date table when imported into Power BI.
- The report should use these measures consistently across KPI cards, trend visuals, and platform comparison charts.
