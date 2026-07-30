# Task 3 Write-up: Git-backed Job Scheduling

## Databricks Job Run URL

Paste the URL of your successful Job run from the Databricks UI address bar:

`https://adb-7405619530719547.7.azuredatabricks.net/jobs/591256975661340/runs/296764459619110?o=7405619530719547`

## Screenshots

Ensure the following screenshot files exist in `task-3/screenshots/`:

1. `job_config.png` — Showing the dbt task configuration with Git repository URL, branch `main`, path `task-2`, and warehouse `hyf-dbt-warehouse`.
2. `job_run_success.png` — Showing a successful run log with a green checkmark and stdout execution output.
3. `job_schedule_paused.png` — Showing the scheduled trigger set to **Paused**.

## Orchestration Comparison

### When would you choose Databricks Jobs versus Apache Airflow for pipeline orchestration?

Write two to three sentences comparing Databricks Jobs and Apache Airflow in your own words:

`I would use Databricks Jobs when the pipeline mainly runs inside Databricks and depends on Databricks SQL, Delta tables, notebooks, or dbt. I would choose Apache Airflow when the workflow has to coordinate many different systems, services, and dependencies outside Databricks, because Airflow is more flexible as a general-purpose orchestrator.`
