### Aggregation Strategy

To support analytics and reporting, data should be aggregated on the following levels:

  - **Daily KPIs**: clicks, FTDs (First Time Deposits), earnings, commission share

These aggregations align with business use cases such as trend monitoring, partner performance comparison, and traffic source optimization.

---

### Entity Relationship Modeling

The API provides multiple entities that can be modeled as relational tables:

- **`earnings`** (fact table): contains metrics like `clicks`, `ftds`, `earnings`, `commission_share`, etc.
- **`partners`** (dimension table): contains partner-related metadata.
- **`brands`** (dimension table): refers to advertisers or products being promoted.
- **`sites`** (dimension table): campaign-level or traffic source identifiers.
- **(Optional) `currency_rates`**: for normalizing financial data across currencies.
