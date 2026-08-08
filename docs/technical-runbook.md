# Technical Runbook: Noodles Crypto Analytics

## System Overview

Python-based ETL pipeline loading currency data into MySQL (`noodles_dw`), with Power BI dashboards for executive reporting through ODBC or a MySQL connector.

## Daily Operations

### 1. Manual ETL Execution

```powershell
.\.venv\Scripts\Activate.ps1
python -m jupyter nbconvert --execute .\scripts\06_powerbi_prep.ipynb
```

Expected duration: 5–10 minutes.

Success indicators:
- Exit code: 0
- Pipeline completes without errors
- Validation checks pass

### 2. Power BI Refresh

1. Open Power BI Desktop.
2. Open the required `.pbix` report from `powerBI/`.
3. Verify the MySQL/ODBC connection.
4. Select Home → Refresh.
5. Check visuals, filters, relationships, and drill-through.

## Demo Recording

For the final approximately 10-minute recording, cover:

1. Project objective and business problem
2. Architecture and data flow
3. Data warehouse/model
4. ETL and data-quality validation
5. Power BI model and relationships
6. Executive dashboard
7. Time-series and platform analysis
8. Currency drill-through
9. Key insights
10. Technical skills and next steps

The supplied recording is currently approximately 6 minutes 9 seconds and should be extended or replaced for the final assessment.

## Monitoring & Validation

Re-run validation cells in `scripts/06_powerbi_prep.ipynb`. Expected checks include:

- No orphaned records
- Expected row counts
- Referential integrity checks pass
- Date coverage is valid

## Troubleshooting

### Python ImportError

Install the project dependencies, for example:

```powershell
pip install pandas sqlalchemy pymysql python-dotenv matplotlib seaborn jupyter
```

### Database connection failure

- Confirm MySQL is running.
- Verify local credentials through environment variables.
- Confirm the `noodles_dw` database exists.

Never commit passwords, `.env` files, or connection secrets.

### Power BI refresh failure

- Verify the local data source.
- Check MySQL/ODBC connectivity.
- Re-enter local credentials if required.

## Database Information

- Database: `noodles_dw`
- Server: local development environment
- Authentication: local MySQL credentials supplied outside Git

## Backup & Recovery

Back up the MySQL database using the organization's approved MySQL backup procedure. Keep database credentials and backups outside the public repository.
