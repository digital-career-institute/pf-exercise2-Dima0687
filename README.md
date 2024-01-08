Objective: To comprehend the significance of primary keys and foreign keys in database management, emphasizing their role

Scenario:
Imagine you are designing a database system for a psychology clinic that manages information about patients, psychologists, and their appointments. You'll be working with tables related to patients and psychologists.

Requirements:

Database Management System (DBMS) software (e.g., MySQL, PostgreSQL, SQLite)
Basic SQL knowledge
Tasks:

Create a Table with Private Key and Foreign Key:

Create a table named Patients with the following columns:
PatientID as a private key (representing a unique identifier for each patient)
Other relevant columns like Name, Age, Gender, etc.
Add a foreign key constraint referencing the Psychologists table (Assume a column PsychologistID exists in the Patients table and references the PsychologistID column in the Psychologists table).
Drop Both Keys:

Write SQL commands to drop the primary key constraint and the foreign key constraint from the Patients table.
Add Primary Key:

Alter the Patients table to add a new primary key constraint on the PatientID column.
Add Composite Primary Key:

Create a composite primary key on the PatientID and AppointmentDate columns to uniquely identify appointments (considering the need for appointment scheduling in the future).
Drop Foreign Key:

Remove the foreign key constraint from the Patients table that references the Psychologists table.
Add Foreign Key:

Add a new foreign key constraint on the Patients table, referencing the Psychologists table.

```SQL
CREATE TABLE psychologist (PsychologistID INT PRIMARY KEY AUTO_INCREMENT, PsychologistName VARCHAR(255));

CREATE TABLE patients (PatientID INT PRIMARY KEY AUTO_INCREMENT, Name VARCHAR(100) NOT NULL, Age INT NOT NULL, Gender VARCHAR(25) NOT NULL, AppointmentDate DATE, PsychologistID INT, FOREIGN KEY(PsychologistID) REFERENCES Psychologist(PsychologistID)  );

ALTER TABLE patients MODIFY PatientID INT;
ALTER TABLE patients DROP PRIMARY KEY;

ALTER TABLE patients ADD PRIMARY KEY (PatientID, AppointmentID);

ALTER TABLE patients DROP FOREIGN KEY patients_ibfk_1;
ALTER TABLE patients DROP FOREIGN KEY patients_ibfk_2;

ALTER TABLE patients ADD FOREIGN KEY ( PsychologistID ) REFERENCES psychologist ( PsychologistID );
```
