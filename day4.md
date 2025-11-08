Learnt Limit & Offest:
1. Display the first 5 patients from the patients table.
2. Show patients 11-20 using OFFSET.
3. Get the 10 most recent patient admissions based on arrival_date.

Solutions:
1, use challenge;
select * from patients limit 5;

2, use challenge;
select * from patients
limit 10 offset 10;

3, use challenge;
select patient_id from patients
order by arrival_date asc
limit 10;

Question: Find the 3rd to 7th highest patient satisfaction scores from the patients table, showing patient_id, name, service, and satisfaction. Display only these 5 records.

use challenge;
select patient_id,name,service,satisfaction from patients
order by satisfaction desc
limit 5 offset 2;
