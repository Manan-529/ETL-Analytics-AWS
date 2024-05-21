# Spotify Data Pipeline with AWS Glue and QuickSight

## Project Overview
This project demonstrates an ETL pipeline to process and visualize Spotify data using AWS services.

## Architecture
![Architecture Diagram](architecture/Architecture.png)

# Steps to Reproduce

##1. **Upload Data to S3**:

# S3 Bucket Structure

### Staging Bucket
- **Name**: `staging`
- **Purpose**: This bucket serves as the staging area for raw data before it's processed by the ETL pipeline.
- **Organization**: Raw data files are uploaded to the root of the bucket, with each file representing a specific data source.

### Data Warehouse Bucket
- **Name**: `warehouse`
- **Purpose**: Transformed data from the ETL pipeline is stored in this bucket for further analysis and visualization.
- **Organization**: Data is organized into folders corresponding to different datasets.

### Access Controls
- **Bucket Policies**: Only authorized IAM users or roles have access to read from or write to the buckets.
- **Encryption**: Data is encrypted at rest using AWS S3 encryption features to ensure security.

### Best Practices
- **Versioning**: Versioning is enabled on both buckets to maintain a history of changes and prevent accidental data loss.
- **Lifecycle Policies**: Lifecycle policies are applied to move data to cheaper storage tiers.

## 2. **Set Up AWS Glue Jobs**: [Script and Configuration](glue_jobs/)<br>

## 3. **Run AWS Glue Crawler**<br>

## 4. **Query Data with Amazon Athena**:

### Example Query
```sql
SELECT artist_id, track_name FROM warehouse
WHERE genre = "LoFi"
GROUP BY artist_id
ORDER BY streams DESC;
```
<br>
## 5. **Visualize Data with QuickSight**
