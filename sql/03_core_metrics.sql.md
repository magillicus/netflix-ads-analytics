--Total Sessions
SELECT COUNT(*) AS total_sessions
FROM streaming_ads_sessions;

--Total Users
SELECT COUNT(DISTINCT user_id) AS total_users
FROM streaming_ads_sessions;

--Total Ad Impressions
SELECT SUM(ad_impressions) AS total_ad_impressions
FROM streaming_ads_sessions;

--Total Ad Revenue
SELECT SUM(ad_revenue) AS total_ad_revenue
FROM streaming_ads_sessions;

--Average Revenue Per User
SELECT
SUM(ad_revenue) / COUNT(DISTINCT user_id) AS arpu
FROM streaming_ads_sessions;

--Average Ads Per Session
SELECT
AVG(ad_impressions) AS avg_ads_per_session
FROM streaming_ads_sessions;

--Ad Completion Rate
SELECT
SUM(ad_completions) * 1.0 / SUM(ad_impressions) AS ad_completion_rate
FROM streaming_ads_sessions;