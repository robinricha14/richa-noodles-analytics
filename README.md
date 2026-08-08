# NoodlesCrypto — Power BI Analytics Project

## Overview

This project delivers an end-to-end BI/DA analytics solution for monitoring cryptocurrency engagement across Twitter and Reddit.

The solution combines Python data preparation, a MySQL dimensional warehouse, reporting views, DAX, and Power BI dashboards.

## Core Deliverables

- Power BI executive dashboard
- Top-performer Power BI report
- Architecture diagram
- Expanded data dictionary
- Technical runbook
- User guide
- DAX measure documentation
- Demo presentation
- Demo video
- LinkedIn post draft
- Portfolio documentation

## Data Sources and Reporting Model

The reporting layer uses:

- `DimDate`
- `DimCurrency`
- `DimPlatform`
- `FactSocialEngagement`
- market/activity fact data
- reporting and aggregation views including executive, time-series, social, and platform analysis

See [`data-dictionary.xlsx`](data-dictionary.xlsx) for the field-level inventory.

## Dashboard Features

- Executive KPIs
- Time-series engagement trends
- Twitter vs Reddit platform comparisons
- Currency-level drill-down
- Date slicers
- Top-N analysis
- Drill-through navigation
- Conditional formatting
- Professional dashboard layout

## Demo

The current `demo-video.mp4` is included in this folder and is approximately 6 minutes 9 seconds long. For the final submission, extend or replace it with an approximately 10-minute walkthrough covering the complete pipeline and dashboard experience.

See [`technical-runbook.md`](technical-runbook.md) for the recommended recording sequence.

## Portfolio Links

- [Project README](../README.md)
- [Technical Runbook](technical-runbook.md)
- [Data Dictionary](data-dictionary.xlsx)
- [LinkedIn Draft](linkedIn_draft.md)
- [Demo Presentation](demo-presentation.pptx)
- [Demo Video](demo-video.mp4)
