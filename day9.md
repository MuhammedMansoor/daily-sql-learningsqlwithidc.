Date Intelligence:
1. Extract the year from all patient arrival dates.
2. Calculate the length of stay for each patient (departure_date - arrival_date).
3. Find all patients who arrived in a specific month.

1,USE challenge;
SELECT patient_id,year(arrival_date) as Arrival_Year from patients;

2,USE challenge;
select patient_id, datediff(departure_date,arrival_date) as length_of_stay from patients;

3,USE challenge;
select patient_id,monthname(arrival_date) as montha from patients;


Challenge:
Calculate the average length of stay (in days) for each service, showing only services where the average stay is more than 7 days. Also show the count of patients and order by average stay descending.USE challenge;
SELECT Service,avg(datediff(departure_date,arrival_date)) as Avg_Stay,count(patient_id) as patientcount from patients
group by service
having	Avg_stay>7
order by Avg_stay desc;
