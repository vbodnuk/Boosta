# GCP Pipeline: Voonix Synthetic Data Loader (Notebook-based)

This pipeline ingests synthetic JSON data into BigQuery using a notebook running in Google Cloud BigQuery UI (Jupyter environment).

## Workflow Summary

- Synthetic JSON files are uploaded to Google Cloud Storage.
- The notebook `data_ingesting.ipynb`:
  - Lists files in the bucket.
  - Extracts table names from file names.
  - Loads data into corresponding BigQuery tables (e.g., `raw_layer.site_earnings`).

## Technologies Used

- Google Cloud Storage
- BigQuery Python Client (`google.cloud.bigquery`)
- Jupyter Notebook (hosted in BigQuery UI)

## Current Status

✅ Data successfully loaded into the `raw_layer` dataset.

🚧 Daily automation via Cloud Scheduler / Composer planned for future improvement.

## File Naming Logic

Each file is named as:

- `advertiser_earnings_synthetic.json`
- `site_earnings_synthetic.json`

The notebook strips `data_ingesting` and loads into:

- `raw_layer.advertiser_earnings`
- `raw_layer.site_earnings`
