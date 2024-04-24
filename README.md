# DBMS-Expt04

## Aim
To develop an application with SQL and programming language using database connectivity. 
### 1. How many appointments are scheduled for each doctor?

#### Program
```SELECT DoctorID, COUNT(AppointmentID) AS TotalAppointments
FROM Appointments
GROUP BY DoctorID;
```
#### Output
### 2.How many appointments are scheduled for each patient?

#### Program
```SELECT PatientID, COUNT(AppointmentID) AS TotalAppointments
FROM Appointments
GROUP BY PatientID;
```
#### Output
### 3.What is the average dosage prescribed for each medication?

#### Program
```SELECT Medication, AVG(CAST(Dosage AS float)) AS AvgDosage
FROM Prescriptions
GROUP BY Medication;
```
#### Output
### 4.Write a SQL query to find the Fruit with the lowest available quantity.

#### Program
```SELECT name AS fruit_name, inventory AS lowest_quantity
FROM fruits
ORDER BY inventory ASC
LIMIT 1;
```
#### Output
### 5.Write a SQL query to find the maximum purchase amount.

#### Program
```SELECT MAX(purch_amt) AS MAXIMUM
FROM orders;
```
#### Output
### 6.Write a SQL query to find What is the age difference between the youngest and oldest employee in the company.

#### Program
```
SELECT MAX(age) - MIN(age) AS age_difference
FROM employee;
```
#### Output
### 7.Write a SQL query to find the number of employees who are having the same age removing the duplicate values.

#### Program
```
SELECT COUNT(DISTINCT age) AS COUNT
FROM employee;
```
#### Output
### 8.Write the SQL query that achieves the grouping of data by age, calculates the minimum income for each age group, and includes only those age groups where the minimum income is less than 1,000,000.

#### Program
```
SELECT age, MIN(income) AS Income
FROM employee
GROUP BY age
HAVING MIN(Income) < 1000000;
```
#### Output
### 9.Write the SQL query that accomplishes the grouping of data by joining date (jdate), calculates the average work hours for each date, and excludes dates where the average work hour is not less than 10.

#### Program
```SELECT jdate, AVG(workhour) AS "AVG(workhour)"
FROM employee1
GROUP BY jdate
HAVING "AVG(workhour)" < 10;
```
#### Output
### 10.Write the SQL query that achieves the selection of category and calculates the sum of the product of price and category ID as Revenue for each category from the "products" table, and includes only those products where the total revenue is greater than 25.

#### Program
```
SELECT category_id, SUM(price * category_id) AS Revenue
FROM products
GROUP BY category_id
HAVING SUM(price * category_id) > 25;
```
#### Output
## Result
Thus , to develop an application with SQL and programming language using database connectivity is successfully done.
