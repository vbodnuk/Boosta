There are two main approaches to storing and processing the data from the Voonix API:

#### Option 1: SQL-Based (e.g., Azure SQL, PostgreSQL, BigQuery)
- **Raw Layer**: API responses are stored as-is for traceability and reprocessing.
- **Staging Layer**: Basic transformations, normalization.
- **Clean Layer**: Business logic is applied, KPIs are calculated, and data is ready for consumption.
- **Analytics Layer**: Final data models (views, materialized views, or marts) for dashboards and reports.

Access:
- Power BI: DirectQuery or Import mode
- Internal systems: via REST/gRPC APIs, or direct SQL queries

#### Option 2: Data Lake (e.g., Azure Data Lake, AWS S3)
- Data is stored in containers representing raw, staging, and clean layers
- File formats: CSV, JSON, or Parquet
- Processing is done using PySpark, Databricks.

Access:
- BI tools: via Parquet or Delta Lake connectors
- Other systems: using scripts or different programming languages
