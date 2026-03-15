--Revenue by Device
SELECT
device_type,
SUM(ad_revenue) AS revenue,
SUM(ad_impressions) AS impressions,
AVG(watch_minutes) AS avg_watch_time
FROM streaming_ads_sessions
GROUP BY device_type
ORDER BY revenue DESC;

--Revenue by Genre
SELECT
content_genre,
SUM(ad_revenue) AS revenue,
SUM(ad_impressions) AS impressions,
AVG(watch_minutes) AS avg_watch_time
FROM streaming_ads_sessions
GROUP BY content_genre
ORDER BY revenue DESC;

--Revenue by Country
SELECT
country,
SUM(ad_revenue) AS revenue,
SUM(ad_impressions) AS impressions
FROM streaming_ads_sessions
GROUP BY country
ORDER BY revenue DESC;

--Engagement vs Ad Load
SELECT
ad_impressions,
AVG(watch_minutes) AS avg_watch_minutes,
COUNT(*) AS sessions
FROM streaming_ads_sessions
GROUP BY ad_impressions
ORDER BY ad_impressions;

