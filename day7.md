Having:
1. Find services that have admitted more than 500 patients in total.
2. Show services where average patient satisfaction is below 75.
3. List weeks where total staff presence across all services was less than 50.

Sol
1, use	challenge;
SELECT service from services_weekly
group by service
having sum(patients_admitted)>500;


2, use	challenge;
SELECT service from patients
group by service
having avg(satisfaction)<75;

3, Use challenge;
SELECT week from staff_schedule
group by week
having sum(present)<50;

Challenge: Question: Identify services that refused more than 100 patients in total and had an average patient satisfaction below 80. Show service name, total refused, and average satisfaction.

Sol:use challenge;
SELECT Service,sum(Patients_refused) as Total_Refused, avg(patient_satisfaction) as AVGSAT FROM services_weekly
group by service
having Total_Refused>100 and AVGSAT<80;
