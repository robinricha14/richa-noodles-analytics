# Noodles Crypto Analytics — Task 9 Portfolio Project

An end-to-end Business Intelligence and Data Analytics project that transforms fragmented cryptocurrency market and social-engagement data into a trusted analytics platform and executive-ready Power BI dashboards.

## Project Overview

The solution demonstrates the full analytics lifecycle:

**Source data → Python ETL → MySQL data warehouse → reporting views → Power BI dashboards → executive insights**

The project combines Python-based data preparation, dimensional data modeling, SQL/MySQL warehousing, DAX, and Power BI to support analysis of cryptocurrency performance and social engagement across Twitter and Reddit.

### Business objectives

- Create a reliable, centralized analytics foundation for crypto data.
- Compare engagement and performance across platforms and currencies.
- Identify top-performing assets and momentum patterns.
- Provide interactive executive dashboards for faster decision-making.
- Document the solution so another analyst can understand and reproduce the workflow.

## Key Outcomes

- Built a star-schema warehouse with currency, date, and platform dimensions.
- Created fact and reporting views for market and social analytics.
- Added validation and data-quality checks to the preparation workflow.
- Developed interactive Power BI dashboards with KPIs, time-series analysis, platform comparisons, and currency drill-through.
- Documented the technical architecture, data dictionary, DAX measures, runbook, and stakeholder usage.

## Technology Stack

| Layer | Technology |
|---|---|
| Data preparation | Python, Jupyter |
| Data warehouse | MySQL |
| Connectivity | ODBC / MySQL connector |
| BI & visualization | Microsoft Power BI |
| Analytics | DAX |
| Documentation | Markdown, Excel, PowerPoint |
| Version control | Git / GitHub |

## Repository Structure

```text
├── README.md
├── docs/
├── powerBI/
├── scripts/
└── screenshots/
```

## Architecture

![Architecture Diagram](docs/architecture-diagram.png)

The pipeline separates ingestion, transformation, warehouse storage, reporting views, and presentation. This makes the solution easier to validate, maintain, and extend.

See [`docs/technical-runbook.md`](docs/technical-runbook.md).

## Data Model

The analytics model uses a dimensional structure centered on:

- `DimCurrency`
- `DimDate`
- `DimPlatform`
- `FactSocialEngagement`
- market/activity fact data
- reporting and aggregation views

The model supports time-based analysis, platform comparisons, currency-level drill-down, and reusable Power BI measures.

The expanded data dictionary is available at [`docs/data-dictionary.xlsx`](docs/data-dictionary.xlsx).

## Power BI Dashboards

### Executive Dashboard

`powerBI/NoodlesCrypto_ExecutiveDashboard.pbix`

Focuses on executive KPIs, market and engagement trends, platform performance, currency-level analysis, and drill-through exploration.

### Top Performers

`powerBI/NoodlesCrypto_TopPerformers.pbix`

Focuses on Top-N analysis, engagement performance, ranking, platform share, and interactive filtering.

Dashboard screenshots are available in [`screenshots/`](screenshots/).

## Key Insights

- Bitcoin remains an influential reference point for overall market movement.
- Social engagement can provide a useful signal for attention and momentum.
- Platform-level comparisons reveal differences in engagement behavior.
- Currency drill-down makes it easier to investigate individual assets.
- A centralized warehouse and validated reporting views improve consistency between raw data and executive reporting.

These findings are analytical observations from the project dataset rather than investment recommendations.

## Setup

### Prerequisites

- Python 3.x
- Jupyter Notebook
- MySQL
- Power BI Desktop
- MySQL/ODBC connectivity
- Required Python packages used by the notebooks

### Python environment

Example Windows setup:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install pandas sqlalchemy pymysql python-dotenv matplotlib seaborn jupyter
```

### Data preparation

Open `scripts/06_powerbi_prep.ipynb` and run the documented preparation and validation workflow. For warehouse design, see `scripts/Task5–Design_Your_Data_Warehouse.ipynb`.

### MySQL

The project expects a MySQL database named `noodles_dw`. Connection credentials should be supplied through the local environment rather than committed to GitHub.

See [`docs/technical-runbook.md`](docs/technical-runbook.md) for refresh, validation, troubleshooting, and recovery procedures.

### Power BI

1. Open the required `.pbix` file from `powerBI/`.
2. Configure the MySQL/ODBC data source for the local environment.
3. Refresh the model.
4. Verify dashboard visuals, filters, relationships, and drill-through behavior.

## Documentation

| Document | Purpose |
|---|---|
| [`docs/technical-runbook.md`](docs/technical-runbook.md) | ETL, refresh, validation, troubleshooting |
| [`docs/data-dictionary.xlsx`](docs/data-dictionary.xlsx) | Tables, fields, types, and descriptions |
| [`docs/user-guide.md`](docs/user-guide.md) | Dashboard usage |
| [`docs/powerbi-report-guide.md`](docs/powerbi-report-guide.md) | Power BI report walkthrough |
| [`docs/dax-measures-list.md`](docs/dax-measures-list.md) | DAX measure inventory |
| [`docs/dax-measures-reference.md`](docs/dax-measures-reference.md) | DAX definitions and explanations |
| [`docs/executive-dashboard-guide.md`](docs/executive-dashboard-guide.md) | Executive dashboard guide |
| [`docs/portfolio.md`](docs/portfolio.md) | Portfolio presentation |
| [`docs/demo-presentation.pptx`](docs/demo-presentation.pptx) | Demo slide deck |
| [`docs/linkedIn_draft.md`](docs/linkedIn_draft.md) | LinkedIn post draft |
| [`docs/task9-feedback-resolution.md`](docs/task9-feedback-resolution.md) | Assessment feedback resolution |

## Demo

The repository contains a recorded walkthrough at [`docs/demo-video.mp4`](docs/demo-video.mp4). The current recording is approximately 6 minutes 9 seconds; for the final assessment, replace or extend it to approximately 10 minutes and cover the architecture, data flow, validation, Power BI model, dashboards, and key insights.

Recommended sequence: project objective → architecture → data warehouse/model → ETL and validation → Power BI model → executive dashboard → time-series/platform analysis → currency drill-through → key insights → technical skills and next steps.

## GitHub Repository

**Public repository:** https://github.com/robinricha14/richa-noodles-analytics

The repository is public. Do not commit credentials, `.env` files, database passwords, or other secrets.

## LinkedIn Post

A ready-to-use LinkedIn post is included in [`docs/linkedIn_draft.md`](docs/linkedIn_draft.md), highlighting the project's BI, ETL, data-modeling, DAX, Power BI, and documentation work.

## Portfolio Skills Demonstrated

- Data warehouse design
- Python ETL and validation
- SQL/MySQL
- Dimensional modeling
- Power BI
- DAX
- Dashboard design
- Data storytelling
- Technical documentation
- Stakeholder-oriented reporting

## Final Submission Checklist

- [x] README includes the public GitHub repository URL.
- [x] GitHub repository is public.
- [x] Architecture diagram included.
- [x] Data dictionary included.
- [x] Technical runbook included.
- [x] LinkedIn post draft included.
- [x] Demo presentation included.
- [x] Demo video file included.
- [ ] Demo video extended/re-recorded to approximately 10 minutes.
- [ ] If required by the assessor, add the hosted demo-video URL after uploading the final recording.
- [ ] Verify all links and remove any credentials/secrets before final submission.

## License / Portfolio Use

This project is presented as a portfolio and educational analytics project. Add an appropriate license before public publication if required by the course, organization, or source-data terms.