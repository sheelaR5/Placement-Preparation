DAY-1
User Retention:

WITH cte AS
(SELECT DISTINCT user_id
FROM user_actions
WHERE EXTRACT(MONTH FROM event_date)=7
AND EXTRACT(YEAR FROM event_date)=2022
INTERSECT
SELECT DISTINCT user_id
FROM user_actions
WHERE EXTRACT(MONTH FROM event_date)=6
AND EXTRACT(YEAR FROM event_date)=2022)
SELECT '7'AS month, COUNT(user_id)AS monthly_active_user
FROM cte;
