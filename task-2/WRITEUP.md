# Task 2 write-up: incremental build timings & Delta history

Fill in after running `dbt build --select fct_trips --full-refresh` baseline followed by `dbt build --select fct_trips` incremental rerun against Databricks.

## First build (full / initial load with --full-refresh)

- **Wall-clock time:** 2m 38.05s
- **Notes:** The full-refresh build completed successfully with `PASS=4 WARN=0 ERROR=0`. Before the successful run, I fixed the Databricks source schema from `public` to `nyc_yellow` and rebuilt the staging views.

## Second build (incremental rerun)

- **Wall-clock time:** 2m 25.82s

## Why was the second run faster?

Write two or three sentences in your own words (see the assignment for the concepts you must name):

`The second run was slightly faster because `is_incremental()` evaluated to true and applied a filter using the maximum `pickup_datetime` already stored in `{{ this }}`. As a result, only rows with a strictly later timestamp were passed to the `MERGE`, instead of rebuilding the whole table. The difference was modest because Databricks still had to evaluate the upstream view, execute the merge, and run the model tests.`

## Delta Table History (DESCRIBE HISTORY)

Paste the output or summary of `DESCRIBE HISTORY hyf.dev_yourname.fct_trips` (showing `CREATE OR REPLACE TABLE` and `MERGE` operations) or reference a screenshot:

`See `delta_history.png`. The Delta table history shows a `CREATE OR REPLACE TABLE AS SELECT` operation for the initial `--full-refresh` build, followed by a `MERGE` operation for the incremental rerun. This confirms that the second build updated the existing Delta table rather than recreating it.`
