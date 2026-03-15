-- =========================================================

-- File: 01_data_exploration.sql
-- Project: Streaming Platform Ad Performance Analytics

-- Purpose:
-- Perform initial exploration of the raw streaming session dataset.
-- This script validates dataset structure, checks row counts,
-- examines distributions across key dimensions (country, device,
-- content genre), and confirms data quality before analysis begins.

-- Output:
-- Basic dataset diagnostics used to verify that the dataset
-- has been loaded correctly and is suitable for downstream
-- metrics development and analytical queries.

-- =========================================================

--Data preview

SELECT *
FROM streaming_ads_sessions
LIMIT 20;

--Row Count
SELECT COUNT(*) AS total_rows  
FROM streaming_ads_sessions;

--Distinct Users
SELECT COUNT(DISTINCT user_id) AS unique_users
FROM streaming_ads_sessions;

--Device distribution
SELECT
device_type,
COUNT(*) AS sessions
FROM streaming_ads_sessions
GROUP BY device_type
ORDER BY sessions DESC;

--Genre distribution
SELECT
content_genre,
COUNT(*) AS sessions
FROM streaming_ads_sessions
GROUP BY content_genre
ORDER BY sessions DESC;

--Country distribution
SELECT
country,
COUNT(*) AS sessions
FROM streaming_ads_sessions
GROUP BY country
ORDER BY sessions DESC;

--Engagement overview
SELECT
AVG(watch_minutes) AS avg_watch_minutes,
AVG(ad_impressions) AS avg_ads_per_session,
AVG(ad_revenue) AS avg_revenue_per_session
FROM streaming_ads_sessions;