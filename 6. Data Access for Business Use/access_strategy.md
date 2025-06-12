### Dashboards

Data will be made available for dashboards (e.g., Power BI, Looker Studio, Tableau) via:
- **Direct SQL DB connections** (DirectQuery or Import mode)
- **Data Lake access** using Parquet files for optimized read performance
- **API or gRPC** connections for real-time or embedded data in internal tools

### Access for Marketing & Product Teams

Depending on the technical skills and tooling available to business users:
- **Power BI dashboards** with role-based access can be used by both technical and non-technical staff
- **Views and Datamarts** in the database can serve as trusted data sources for ad hoc exploration
- **Embedded analytics or internal tools** can fetch and visualize data using gRPC or REST APIs

### Ad Hoc Analysis

Analysts or data-savvy users can use:
  - **Direct database connections** (SQL-based tools)
  - **Pre-aggregated exports** (e.g., in CSV or Excel) for offline analysis

### Performance & Freshness Best Practices

#### SQL Database:
- Use **indexes** on filter/join keys
- Regularly monitor and **rebuild or reorganize index fragmentation** to maintain efficient query performance
- Use **EXEC sp_recompile** or update statistics to **refresh execution plans** after significant data or query changes
- Apply **CTEs** or temp tables to avoid re-calculating subqueries

#### Data Lake:
- Store data in **Parquet** format instead of CSV/JSON for better I/O performance
- Implement **partitioning** by date or other frequent filter fields
- Use **Delta Lake** or equivalent if transactional updates are needed

#### Power BI:
- Avoid **Import mode** for large datasets — prefer **DirectQuery** to reduce memory load and ensure data freshness.
- Minimize complex **DAX expressions**; offload calculations to SQL/data layer where possible for better performance and maintainability.
