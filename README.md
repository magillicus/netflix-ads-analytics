# Streaming Platform Ad Performance Analytics

This project explores analytics frameworks that could support performance monitoring for a streaming advertising platform.

## Dashboard Preview
<img width="959" height="539" alt="Tableau Dashboard Screenshot" src="https://github.com/user-attachments/assets/d96214b8-f9f1-4466-9d9a-42a5898c15f1" />

## Executive Summary Presentation
[Netflix Streaming Ad Platform Performance Analysis.pdf](https://github.com/user-attachments/files/26034068/Netflix.Streaming.Ad.Platform.Performance.Analysis.pdf)

## Project Overview

This project explores advertising performance within a simulated ad-supported streaming platform. The analysis evaluates how advertising revenue, viewer engagement, and content consumption interact across different devices, content genres, and geographic markets.

Using a dataset representing 25,000 streaming sessions, the project develops core platform metrics, analyzes monetization patterns, and visualizes insights through an interactive Tableau dashboard. The goal is to demonstrate how analytics can support product and advertising strategy decisions for a streaming platform.

Key components of the project include:

* SQL-based data exploration and metric development
* Aggregated analysis of advertising revenue drivers
* Visualization of platform performance using Tableau
* Executive-style summary of key findings and strategic insights

This project simulates the type of analytical work that might support product and advertising teams responsible for monitoring the health and performance of a streaming ad platform.

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

## Project Workflow

1. **Data Exploration (SQL)**
   The raw streaming session dataset was explored and validated to confirm distributions across devices, content genres, and countries.

2. **Metrics Development (SQL)**
   A metrics layer was created to calculate engagement and monetization indicators such as ad completion rate, revenue per impression, and watch duration.

3. **Aggregation & Supporting Analysis (Excel)**
   Query outputs were exported into Excel to prepare structured tables used for visualization.

4. **Visualization (Tableau)**
   An interactive dashboard was built to monitor advertising platform health, revenue distribution, and engagement patterns.

5. **Executive Communication (PowerPoint)**
   Key findings were summarized into an executive-style presentation highlighting insights and strategic opportunities.


## Tools Used

* SQL
* Excel
* Tableau
* GitHub

