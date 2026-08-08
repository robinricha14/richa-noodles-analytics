# Technical Runbook: Noodles Crypto Analytics

## System Overview

Python-based ETL pipeline loading currency data into MySQL (`noodles_dw`), with Power BI dashboards for executive reporting (connect via ODBC or MySQL connector).

## Daily Operations

### 1. Manual ETL Execution

```powershell
# Activate Python environment (Windows)
.\.venv\Scripts\Activate.ps1
# or
.\venv\Scripts\activate.bat

# Run the Task 6 notebook from the repository root
cd .\task-6-python-data-preparation-for-power-bi
python -m jupyter nbconvert --execute .\06_powerbi_prep.ipynb
```

Expected Duration: 5-10 minutes

Success Indicators:
- Exit code: 0
- Log file shows "Pipeline Finished Successfully"
- No errors in `logs/` directory

### 2. Automated Execution (Task Scheduler)

Windows (Task Scheduler):

1. Open Task Scheduler
2. Create Basic Task: "Noodles ETL"
3. Trigger: Daily at 6:00 AM
4. Action: Start program
   - Program: `D:\richaInternship\task 9\noodles-analytics\.venv\Scripts\python.exe`
   - Arguments: `-m jupyter nbconvert --execute .\task-6-python-data-preparation-for-power-bi\06_powerbi_prep.ipynb`
   - Start in: `D:\richaInternship\task 9\noodles-analytics`

### 3. Power BI Refresh

Manual Refresh:

1. Open Power BI Desktop
2. Home → Refresh
3. Wait 30-60 seconds for completion

Scheduled Refresh (Power BI Service):

- Check dataset settings → Refresh history
- Troubleshoot gateway if failures occur

## Demo Recording (recommended)

To produce a demo video that walks through notebooks and Power BI dashboards (screen recording):

1. Open Zoom, OBS Studio, or Microsoft Teams and select a single-screen or application window capture.
2. Start the Task 5 notebook and run the key cells that create dimensions (DimCurrency, DimDate, DimPlatform) and the sample fact load; narrate the purpose of each step.
3. Switch to Power BI Desktop and open `task-8-reports/reports - Task8/NoodlesCrypto_ExecutiveDashboard.pbix`.
4. Walk through the model view (relationships), key visuals, time slicers, and one token deep-dive; show the `vw_ExecutiveDashboard` and `vw_TimeSeries` results where useful.
5. Keep the recording to ~8–12 minutes; save the file as `docs/demo-video.mp4` and replace the existing placeholder.

Notes:
- Record at 720p or 1080p for clarity. Use system audio off and a clear microphone for narration.
- If re-recording is not possible, include a brief README note pointing viewers to the notebooks and `.pbix` files.

## Monitoring & Validation

### Check ETL Logs

```powershell
Get-Content logs\etl_* -Tail 50
Select-String -Pattern "error" logs\etl_*
```

### Validate Data Quality

- Re-run validation cells in `06_powerbi_prep.ipynb`
- Expected output:
  - ✓ No orphaned records
  - ✓ Row counts match expectations
  - ✓ All referential integrity checks pass

## Troubleshooting

### Issue: Python script fails with ImportError

Symptom: `ModuleNotFoundError: No module named 'pandas'`

Solution:
- `pip install pandas sqlalchemy pymysql python-dotenv matplotlib seaborn`

### Issue: Database connection fails

Symptom: `sqlalchemy.exc.OperationalError`

Solution:
- Check MySQL is running
- Verify credentials in `.env`
- Test connection:

```python
from sqlalchemy import create_engine
engine = create_engine('mysql+pymysql://user:password@localhost/noodles_dw')
print(engine.connect())
```

### Issue: Staging tables empty after ETL

Symptom: Row counts = 0

Solution:
- Check JSON files exist in `data/raw/`
- Verify file permissions
- Review logs for error messages

### Issue: Power BI refresh fails

Symptom: "Data source error"

Solution:
- Verify on-premises gateway is running
- Check gateway logs
- Re-enter credentials in dataset settings

## File Locations

- Source JSON files: `data/raw/`
- Task 5 notebook: `task-5-design-your-data-warehouse/Task5–Design_Your_Data_Warehouse.ipynb`
- Task 6 notebook: `task-6-python-data-preparation-for-power-bi/06_powerbi_prep.ipynb`
- Power BI reports: `task-7-reports/reports/NoodlesCrypto_TopPerformers.pbix`, `task-8-reports/reports - Task8/NoodlesCrypto_ExecutiveDashboard.pbix`
- Task 7 screenshots: `task-7-reports/reports/Screenshots/`
- Task 8 screenshots: `task-8-reports/reports - Task8/Screenshots/`
- Documentation: `docs/`

## Database Information

- Server: localhost
- Database: noodles_dw
- Schemas: Staging, DW
- Authentication: MySQL user from `.env`

## Backup & Recovery

Database Backup:

```sql
BACKUP DATABASE noodles_dw
TO DISK = 'C:\Backups\NoodlesDW_Full.bak'
WITH FORMAT, INIT, NAME = 'Full Backup of noodles_dw';
```

## Code Backup

All code versioned in Git repository.
