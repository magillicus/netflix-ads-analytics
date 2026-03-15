-- =========================================================

-- File: 03_platform_performance_analysis.sql

-- Project: Streaming Platform Ad Performance Analytics

-- Purpose:
-- Analyze overall advertising platform performance using the
-- derived metrics layer. This script evaluates key performance
-- indicators such as revenue, ad impressions, engagement,
-- and session activity across major platform segments.

-- Segmentation dimensions include:
-- - Device type
-- - Content genre
-- - Geographic region

-- Output:
-- Aggregated metrics used to understand platform health,
-- identify revenue drivers, and support dashboard reporting.

-- =========================================================

--Revenue by Device

SELECT
device_type,
COUNT(*) AS sessions,
SUM(ad_impressions) AS impressions,
ROUND(SUM(ad_revenue),2) AS revenue,
ROUND(AVG(watch_minutes),1) AS avg_watch_minutes
FROM ads_metrics_session
GROUP BY device_type
ORDER BY revenue DESC;

--Revenue by Genre
SELECT
content_genre,
COUNT(*) AS sessions,
ROUND(SUM(ad_revenue),2) AS revenue,
SUM(ad_impressions) AS impressions,
ROUND(AVG(watch_minutes),1) AS avg_watch_minutes
FROM ads_metrics_session
GROUP BY content_genre
ORDER BY revenue DESC;

--Revenue by Country
SELECT
country,
COUNT(*) AS sessions,
ROUND(SUM(ad_revenue),2) AS revenue,
SUM(ad_impressions) AS impressions
FROM ads_metrics_session
GROUP BY country
ORDER BY revenue DESC;

--Engagement vs Ad Load
SELECT
ad_impressions,
ROUND(AVG(watch_minutes),1) AS avg_watch_minutes,
COUNT(*) AS sessions
FROM ads_metrics_session
GROUP BY ad_impressions
ORDER BY ad_impressions;

--Top Content by Ad Revenue
SELECT
content_title,
content_genre,
ROUND(SUM(ad_revenue),2) AS revenue,
SUM(ad_impressions) AS impressions
FROM ads_metrics_session
GROUP BY content_title, content_genre
ORDER BY revenue DESC
LIMIT 15;