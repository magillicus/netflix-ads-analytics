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
