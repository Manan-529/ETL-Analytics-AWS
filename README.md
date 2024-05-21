# Spotify Data Pipeline with AWS Glue and QuickSight

## Project Overview
This project demonstrates an ETL pipeline to process and visualize Spotify data using AWS services.

## Architecture
![Architecture Diagram](architecture/architecture_diagram.png)

## Steps to Reproduce
1. **Upload Data to S3**: [Instructions](docs/s3_bucket_structure.md)
2. **Set Up AWS Glue Jobs**: [Script and Configuration](glue_jobs/)
3. **Run AWS Glue Crawler**
4. **Query Data with Amazon Athena**: [Sample Queries](athena_queries/sample_queries.sql)
5. **Visualize Data with QuickSight**: [Setup Guide](docs/quicksight_setup.md)

## QuickSight Dashboards
![Dashboard Screenshot](quicksight/dashboard_screenshot.png)

## Example Queries
```sql
SELECT artist, COUNT(*) AS song_count
FROM "your_database"."your_table"
WHERE year = 2023
GROUP BY artist
ORDER BY song_count DESC;
