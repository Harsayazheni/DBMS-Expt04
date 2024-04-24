# DBMS-Expt04

## Aim
To develop an application with SQL and programming language using database connectivity. 
### 1. How many appointments are scheduled for each doctor?
![Screenshot 2024-04-24 183943](https://github.com/Harsayazheni/DBMS-Expt04/assets/118708467/b7a06ed3-217f-425b-b86f-34b63e61e60e)

#### Program
```SELECT DoctorID, COUNT(AppointmentID) AS TotalAppointments
FROM Appointments
GROUP BY DoctorID;
```
#### Output
![Screenshot 2024-04-24 183954](https://github.com/Harsayazheni/DBMS-Expt04/assets/118708467/018cfc5d-7b7c-4588-9a6b-051f50cb0501)

### 2.How many appointments are scheduled for each patient?
![Screenshot 2024-04-24 184003](https://github.com/Harsayazheni/DBMS-Expt04/assets/118708467/18fbefba-766d-48cb-8812-f672a4e05c5f)

#### Program
```SELECT PatientID, COUNT(AppointmentID) AS TotalAppointments
FROM Appointments
GROUP BY PatientID;
```
#### Output
![Screenshot 2024-04-24 184013](https://github.com/Harsayazheni/DBMS-Expt04/assets/118708467/8b3e58f3-e9de-4a8c-b35f-5da4a8f678ec)

### 3.What is the average dosage prescribed for each medication?
![Screenshot 2024-04-24 184023](https://github.com/Harsayazheni/DBMS-Expt04/assets/118708467/34882206-aa3f-432c-8055-06acc1ea28a6)

#### Program
```SELECT Medication, AVG(CAST(Dosage AS float)) AS AvgDosage
FROM Prescriptions
GROUP BY Medication;
```
#### Output
![Screenshot 2024-04-24 184032](https://github.com/Harsayazheni/DBMS-Expt04/assets/118708467/5f9cc774-f92e-4886-8c0e-9f3e8ada1443)

### 4.Write a SQL query to find the Fruit with the lowest available quantity.
![Screenshot 2024-04-24 184039](https://github.com/Harsayazheni/DBMS-Expt04/assets/118708467/a8498132-67c1-4fbb-8e19-77b0af13e19d)

#### Program
```SELECT name AS fruit_name, inventory AS lowest_quantity
FROM fruits
ORDER BY inventory ASC
LIMIT 1;
```
#### Output
![Screenshot 2024-04-24 184046](https://github.com/Harsayazheni/DBMS-Expt04/assets/118708467/83508b84-cfdb-40ed-8b84-abbd4912d57d)


### 5.Write a SQL query to find the maximum purchase amount.
![Screenshot 2024-04-24 184054](https://github.com/Harsayazheni/DBMS-Expt04/assets/118708467/d192dc73-dfa9-4db5-a549-0e89a3f44229)

#### Program
```SELECT MAX(purch_amt) AS MAXIMUM
FROM orders;
```
#### Output
![Screenshot 2024-04-24 184101](https://github.com/Harsayazheni/DBMS-Expt04/assets/118708467/bddf2601-9f12-468b-bdaa-11e0fa9def92)

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
