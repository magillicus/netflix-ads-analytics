# Streaming Platform Ad Performance Analytics

## Overview

This project explores the design of analytics metrics and reporting workflows for an ad-supported streaming platform. The goal is to evaluate advertising performance, viewer engagement, and revenue generation across streaming sessions.

The analysis simulates how analytics engineers and product analysts might monitor the health of a streaming advertising platform similar to those used by large media companies.

## Business Scenario

A streaming platform has recently launched an advertising-supported subscription tier. Product and business teams need visibility into how ads impact viewer engagement and revenue performance.

This project designs foundational metrics and performs exploratory analysis on streaming session data to understand:

* ad impressions and revenue generation
* viewer engagement patterns
* performance differences across devices, countries, and content genres
* relationships between ad load and viewing behavior

## Objectives

* Define core performance metrics for an advertising-supported streaming platform
* Analyze ad impressions, engagement, and revenue patterns
* Identify content and user segments generating the most advertising value
* Build dashboards and reporting structures for monitoring platform health

## Key Metrics

Core Ad Platform Metrics:

* Total ad impressions
* Total ad revenue
* Average revenue per user (ARPU)
* Ad completion rate
* Average ad impressions per session

Product Health Metrics:

* Average watch minutes per session
* Ads per session
* Revenue by content genre
* Relationship between ad load and viewer engagement

## Dataset

The dataset used in this project is a synthetic streaming session dataset representing approximately 25,000 viewing sessions across multiple countries, devices, and content categories.

Each row represents a streaming session and includes:

* user identifiers
* session metadata
* content attributes
* ad delivery metrics
* advertising revenue

Synthetic data was used to simulate realistic advertising platform behavior while preserving analytical relationships between engagement, ad impressions, and revenue.

## Project Structure

```
data/
    netflix_ad_performance_dataset.csv

sql/
    01_data_exploration.sql
    02_core_metrics.sql
    03_ad_performance_analysis.sql
    04_deep_dive_analysis.sql

excel/
    supporting_analysis.xlsx

tableau/
    ads_platform_dashboard.twbx

presentation/
    ads_platform_insights.pptx
```

## Tools Used

* SQL
* Excel
* Tableau
* GitHub

## Status

This project is currently under development and will include additional analysis, dashboards, and insights as the work progresses.

