# User Guide: Noodles Crypto Dashboards

## Overview

This guide explains how to use the Noodles Crypto Analytics dashboards for market-insight exploration and stakeholder decision-making. No programming knowledge is required for normal dashboard use.

## Accessing the dashboards

### Power BI Desktop

1. Open the required `.pbix` file from `powerBI/`.
2. Confirm the local MySQL/ODBC connection is configured.
3. Select **Home → Refresh** when a current dataset is required.
4. Use the report tabs, slicers, visuals, and drill-through features described below.

### Power BI Service

If the reports have been published to an organization's Power BI workspace, sign in to Power BI Service and open the Noodles Analytics report. Check the **Last Refresh** timestamp before relying on current figures.

## Available dashboards

### 1. Executive Dashboard

**Purpose:** Provide a high-level view of market and engagement performance.

Use it to:
- Review headline KPIs.
- Compare market and engagement trends over time.
- Filter the analysis by date and other available dimensions.
- Identify areas that need deeper investigation.

**How to use it:**
1. Set the required date range with the date slicer.
2. Select a visual to cross-filter related visuals.
3. Hover over chart points for tooltips.
4. Use drill-through where available to investigate a selected currency.

### 2. Top Performers Report

**Purpose:** Identify relative winners, losers, and high-engagement currencies.

Use it to:
- Review Top-N currencies.
- Compare rankings and performance.
- Identify volume and engagement leaders.
- Drill into a specific currency.

**How to use it:**
1. Adjust the Top-N control if available.
2. Select a currency or visual category to filter the page.
3. Use the context menu (`...`) when export is enabled.
4. Drill through to currency-level details where configured.

### 3. Currency / Deep-Dive Analysis

**Purpose:** Investigate one currency in more detail.

Typical views include:
- Price or market trends.
- Trading activity.
- Social engagement.
- Historical comparisons.

Use a currency selector or drill-through from another report page.

## Common tasks

### Filter by date

1. Locate the date slicer.
2. Select a start and end date.
3. Use relative-date options where available, such as a recent period or year-to-date.

### Cross-filter a dashboard

Click a bar, line, KPI category, or table row. Power BI will highlight or filter related visuals when interactions are configured.

### Drill through

Right-click a supported currency or data point and choose the available drill-through page. Use the back button to return to the originating report page.

### Export data

If enabled by the report permissions:
1. Select the visual's `...` menu.
2. Choose **Export data**.
3. Select the available export format.
4. Review the exported data before using it outside the report.

### Export or print a report

Use the Power BI export/print options available in your environment. Confirm that filters are set correctly before exporting.

## Understanding key metrics

| Metric | Meaning | Typical use |
|---|---|---|
| Market capitalization | Aggregate market value represented by the dataset | Understand market scale |
| 24h volume | Recent trading activity | Compare liquidity/activity |
| Price change % | Percentage movement over the selected period | Spot directional movement |
| Moving average | Smoothed time-series measure | Identify broader trends |
| Volatility | Degree of price variation | Compare stability/risk characteristics |
| Social engagement | Activity from supported social platforms | Measure attention and momentum |

## Dashboard tips

**Do:**
- Check the refresh timestamp before important analysis.
- Use filters to narrow the question you are investigating.
- Validate surprising results by drilling into the underlying currency or platform.
- Keep the report's date range visible when sharing screenshots or exports.

**Don't:**
- Treat stale data as current market information.
- Assume correlation proves causation.
- Share confidential report data outside approved channels.
- Treat dashboard observations as investment advice.

## Troubleshooting

### A visual is blank

Check the selected filters, date range, and data-source refresh status. If the report is connected to a local MySQL source, verify the connection before refreshing.

### Values look different from an earlier report

The dataset may have been refreshed or historical records may have changed. Compare the report's refresh timestamp and selected filters.

### Refresh fails

Follow `docs/technical-runbook.md` for database, ODBC, validation, and Power BI troubleshooting steps.

## Support

For technical questions, use the project owner or course/team support channel associated with the deployment. Do not place credentials or secrets in the public GitHub repository.
