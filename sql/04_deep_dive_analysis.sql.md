-- =========================================================

-- File: 04_deep_dive_analysis.sql

-- Project: Streaming Platform Ad Performance Analytics

-- Purpose:
-- Perform deeper analytical exploration of the streaming ads
-- ecosystem to uncover content-level monetization patterns,
-- engagement trends, and advertising efficiency metrics.

-- This script focuses on identifying high-performing content,
-- examining the relationship between ad load and viewer
-- engagement, and evaluating monetization efficiency across
-- different content categories.

-- Output:
-- Insight-oriented queries used to generate findings for
-- dashboards, reports, and executive summaries.

-- =========================================================

--Top Content by Ad Revenue

SELECT
content_title,
content_genre,
SUM(ad_revenue) AS revenue,
SUM(ad_impressions) AS impressions
FROM streaming_ads_sessions
GROUP BY content_title, content_genre
ORDER BY revenue DESC
LIMIT 15;

--Session with Highest Ad Load
SELECT
session_id,
watch_minutes,
ad_impressions,
ad_revenue
FROM streaming_ads_sessions
ORDER BY ad_impressions DESC
LIMIT 20;

--Revenue Efficiency/Revenue per Impression
SELECT
content_genre,
SUM(ad_revenue) / SUM(ad_impressions) AS revenue_per_impression
FROM streaming_ads_sessions
GROUP BY content_genre
ORDER BY revenue_per_impression DESC;
