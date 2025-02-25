# Hands-on: Hive: Web Server Log Analysis with Apache Hive

## Project Overview
This analyses analyzes web server logs stored in CSV format using Apache Hive to derive key metrics including request patterns, error rates, and security insights. Designed for big data environments, it demonstrates Hive's capabilities for processing structured log data at scale while implementing optimizations like partitioning

## Implementation Approach
1. Created external table in Hue
```
CREATE DATABASE web_logs;
USE web_logs;
```
External table SQL code
```
CREATE EXTERNAL TABLE IF NOT EXISTS web_logs_data (
    ip STRING,
    ⁠ timestamp ⁠ STRING,  -- Enclosed in backticks
    url STRING,
    status INT,
    user_agent STRING
)
ROW FORMAT DELIMITED
FIELDS TERMINATED BY ','
STORED AS TEXTFILE
LOCATION 'hdfs:///user/hive/warehouse/web_logs';
```
