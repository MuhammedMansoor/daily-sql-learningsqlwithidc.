Learnt Aggregate:

### Practice Questions:

1. Count the total number of patients in the hospital.
2. Calculate the average satisfaction score of all patients.
3. Find the minimum and maximum age of patients.


Sol:
1, use challenge;
select count(patient_id) as Total_Pts from patients;

2, use challenge;
select avg(satisfaction) as Average_Satisfaction_Score from patients;

3, use challenge;
select min(age) as minimum_age,max(age) as maximum_age from patients;


Question: Calculate the total number of patients admitted, total patients refused, and the average patient satisfaction across all services and weeks. Round the average satisfaction to 2 decimal places.

Sol:
select sum(patients_admitted) as total_patients,sum(patients_refused) as total_refused, round(avg(patient_satisfaction),2) as avg_s from services_weekly;
