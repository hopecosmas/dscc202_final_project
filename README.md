# DSCC202 Final Project – Tweet Sentiment Analytics Pipeline

## Project Overview
This project implements an end-to-end tweet sentiment analytics pipeline using Databricks, Delta Lake, MLflow, and Databricks Dashboards. The pipeline processes raw tweet data through Bronze, Silver, and Gold layers to generate sentiment insights and interactive visualizations.

---

# Architecture

## Bronze Layer
- Ingest raw tweet JSON data using Auto Loader (CloudFiles)
- Enforce schema validation
- Store raw data in Delta format
- Add metadata columns

## Silver Layer
- Extract @mentions using regex
- Clean tweet text
- Parse timestamps
- Explode mentions into individual rows
- Prepare transformed analytics-ready data

## Gold Layer
- Load sentiment model from Unity Catalog
- Apply predictions using Spark UDFs
- Generate binary sentiment classifications
- Create aggregated analytics tables

## Application Layer
- Build materialized views
- Generate positive/negative mention aggregations
- Create top mentioned user analytics

---

# Technologies Used

- Databricks
- Apache Spark
- Delta Lake
- MLflow
- Python
- SQL
- Databricks Dashboards
- Unity Catalog

---

# Dashboard Features

The dashboard includes:

1. Total Tweets
2. Tweets With Mentions
3. Tweets Without Mentions
4. Top 10 Users by Tweet Count
5. Top 10 Most Positively Mentioned
6. Top 10 Most Negatively Mentioned

---

# MLflow Experiment Tracking

The project tracks:

- Accuracy
- Precision
- Recall
- F1 Score
- Confusion Matrix Artifact
- Model Parameters
- Delta Table Version

---

# Automated Workflow

A Databricks Job was configured to:

1. Run the tweet pipeline
2. Refresh dashboard automatically
3. Execute daily at 2:00 AM UTC
