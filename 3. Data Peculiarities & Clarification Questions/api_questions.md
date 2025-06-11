### Data Peculiarities

- It's unclear whether all expected fields are always present in the response payloads. For example, if a value is null or not available, will the key still be included with a null value, or omitted entirely. 
- The documentation does not clearly specify the expected data types (e.g., whether numerical values are returned as strings or floats). This can lead to casting and parsing issues during ingestion.

---

### Questions for API Provider / Product Team

1. **Does the API always return all expected fields, even if their values are null?**  
   → Important for schema consistency and transformation pipelines.

2. **Are there rate limits or quotas we need to respect (per minute, per day)?**  
   → Needed to plan batch frequency.

3. **Is there a guarantee that historical data won’t change retroactively?**  
   → If yes, we may avoid reprocessing past data daily.

4. **Is there pagination or maximum record count per request?**  
   → Important for performance tuning and retry logic.




---

### Why These Questions Matter

From an engineering perspective, predictable structure and typing reduce the complexity of transformations and schema evolution.  
From a business perspective, knowing the accuracy, freshness, and stability of the data helps define how reliable reports and metrics are.






