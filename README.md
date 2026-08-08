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

[`powerBI/NoodlesCrypto_ExecutiveDashboard.pbix`](powerBI/NoodlesCrypto_ExecutiveDashboard.pbix)

Focuses on executive KPIs, market and engagement trends, platform performance, currency-level analysis, and drill-through exploration.

### Top Performers

[`powerBI/NoodlesCrypto_TopPerformers.pbix`](powerBI/NoodlesCrypto_TopPerformers.pbix)

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
| [`docs/architecture-diagram.png`](docs/architecture-diagram.png) | End-to-end technical architecture |
| [`docs/data-dictionary.xlsx`](docs/data-dictionary.xlsx) | Source files, dimensions, facts, aggregations, and fields |
| [`docs/technical-runbook.md`](docs/technical-runbook.md) | ETL, refresh, validation, troubleshooting |
| [`docs/user-guide.md`](docs/user-guide.md) | Dashboard usage for non-technical stakeholders |
| [`docs/demo-presentation.pptx`](docs/demo-presentation.pptx) | 12-slide portfolio/demo presentation |
| [`docs/demo-video.mp4`](docs/demo-video.mp4) | Approximately 10-minute recorded walkthrough |
| [`docs/final-checklist.md`](docs/final-checklist.md) | Final submission checklist |
| [`docs/powerbi-report-guide.md`](docs/powerbi-report-guide.md) | Power BI report walkthrough |
| [`docs/dax-measures-list.md`](docs/dax-measures-list.md) | DAX measure inventory |
| [`docs/dax-measures-reference.md`](docs/dax-measures-reference.md) | DAX definitions and explanations |
| [`docs/executive-dashboard-guide.md`](docs/executive-dashboard-guide.md) | Executive dashboard guide |
| [`docs/portfolio.md`](docs/portfolio.md) | Portfolio presentation |
| [`docs/linkedIn_draft.md`](docs/linkedIn_draft.md) | LinkedIn post draft |
| [`docs/task9-feedback-resolution.md`](docs/task9-feedback-resolution.md) | Assessment feedback resolution |

## Demo

The final demo recording is [`docs/demo-video.mp4`](docs/demo-video.mp4) and has been extended to approximately 10 minutes. The walkthrough covers the project objective, architecture and data flow, data warehouse/model, ETL and validation, Power BI model, dashboards, drill-through analysis, key insights, and technical implementation.

The accompanying [`docs/demo-presentation.pptx`](docs/demo-presentation.pptx) contains the 12-slide presentation structure required for the portfolio demonstration.

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
- [x] Data dictionary included in the project package.
- [x] Technical runbook included.
- [x] Stakeholder user guide included.
- [x] 12-slide demo presentation included in the project package.
- [x] Demo video extended to approximately 10 minutes in the project package.
- [x] LinkedIn post draft included.
- [x] Relative README links point to the intended repository paths.
- [ ] Verify the final binary artifacts are present on GitHub before resubmission.
- [ ] If the assessor requires a separately hosted demo-video URL, add that hosted URL after uploading the final recording.

## License / Portfolio Use

This project is presented as a portfolio and educational analytics project. Add an appropriate license before public publication if required by the course, organization, or source-data terms.