Learnt WHERE icluding Operators and comparison, escape and handling null values.

  Practice Question:
1. Find all patients who are older than 60 years.
    Sol: use challenge;
            SELECT * FROM PATIENTS WHERE AGE>60;
  
2. Retrieve all staff members who work in the 'Emergency' service.
    use challenge;
SELECT * FROM staff WHERE service='Emergency' ;
      
3. List all weeks where more than 100 patients requested admission in any service.
    use challenge;
      SELECT week FROM services_weekly where patients_request>100;



### Daily Challenge:

**Question:** Find all patients admitted to 'Surgery' service with a satisfaction score below 70, showing their patient_id, name, age, and satisfaction score.

  use challenge;
select patient_id,name,age,satisfaction from patients where service='Surgery' and satisfaction<70;


  
  
