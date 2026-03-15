-- =========================================================

-- File: 02_metrics_layer.sql

-- Project: Streaming Platform Ad Performance Analytics

-- Purpose:
-- Create a derived metrics layer from the raw streaming
-- session dataset. This script generates calculated fields
-- such as engagement metrics, ad interaction rates, and
-- revenue efficiency metrics.

-- The resulting table (ads_metrics_session) acts as a clean,
-- analysis-ready dataset that simplifies downstream queries
-- and ensures consistent metric definitions across analyses.

-- Output:
-- ads_metrics_session table containing both raw session data
-- and derived advertising performance metrics.

-- =========================================================

-- Data Preview

SELECT *  
FROM ads_metrics_session  
LIMIT 10;

-- Headline metrics
SELECT
    COUNT(*) AS total_sessions,
    COUNT(DISTINCT user_id) AS total_users,
    SUM(ad_impressions) AS total_ad_impressions,
    ROUND(SUM(ad_revenue), 2) AS total_ad_revenue,
    ROUND(SUM(ad_revenue) * 1.0 / COUNT(DISTINCT user_id), 4) AS arpu,
    ROUND(AVG(ad_impressions), 2) AS avg_ads_per_session,
    ROUND(AVG(watch_minutes), 2) AS avg_watch_minutes,
    ROUND(SUM(ad_completions) * 1.0 / SUM(ad_impressions), 4) AS platform_completion_rate,
    ROUND(SUM(ad_clicks) * 1.0 / SUM(ad_impressions), 4) AS platform_click_rate
FROM ads_metrics_session;