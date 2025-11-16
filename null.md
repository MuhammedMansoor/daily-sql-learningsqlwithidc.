1. Find all weeks in services_weekly where no special event occurred.
2. Count how many records have null or empty event values.
3. List all services that had at least one week with a special event.

1,USE challenge;
SELECT WEEK FROM services_weekly
where event='none';

2, USE challenge;
SELECT Count(*) from services_weekly
where event is null;

3, USE challenge;
Select service from services_weekly
where event is not null and event<>"none"
group by service;


Question: Analyze the event impact by comparing weeks with events vs weeks without events. 
Show: event status ('With Event' or 'No Event'), count of weeks, average patient satisfaction, and average staff morale. Order by average patient satisfaction descending.

USE Challenge;
SELECT
    EventsYN,
    COUNT(*) AS weeks,
    AVG(patient_satisfaction) AS satisfaction,
    AVG(staff_morale) AS morale
FROM (
    SELECT
        week,
        CASE
            WHEN SUM(CASE WHEN event <> 'none' THEN 1 ELSE 0 END) > 0 THEN 'With Event'
            ELSE 'No Event'
        END AS EventsYN,
        AVG(patient_satisfaction) AS patient_satisfaction,
        AVG(staff_morale) AS staff_morale
    FROM services_weekly
    GROUP BY week
) AS week_summary
GROUP BY EventsYN
ORDER BY satisfaction DESC;
