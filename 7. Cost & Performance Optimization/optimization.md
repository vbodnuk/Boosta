#### API Request Strategy:
- Use **batch processing** (e.g., daily scheduled jobs) instead of real-time ingestion to reduce API calls and avoid hitting rate limits.
- Track `last_synced_at` timestamp to only request **delta updates** where supported.


#### Storage Optimization:
- Use **Parquet format** instead of CSV/JSON for compressed and efficient storage (better IO, lower cost).
- Implement **partitioning** for better query pruning in large datasets.

#### Compute Efficiency:
- Prefer **SQL-based transformations** (e.g., with dbt or stored procedures) over runtime transformations in BI tools.
- Schedule **incremental transformations** to avoid full table scans.
- Monitor long-running queries.

#### Stack Recommendation:
- **Batch-based ingestion** (e.g., with Airflow or Azure Data Factory).
- **Blob Storage or Data Lake** with Parquet files.
- **SQL Layer** (e.g., Azure SQL or Synapse) for transformations and analytics.
- **Power BI** with DirectQuery or pre-aggregated import tables.

#### Monitoring & Cost Control:
- Track API usage and set alerts on excessive calls or errors.
- Review and optimize **Power BI query plans** and DAX queries using Performance Analyzer.
