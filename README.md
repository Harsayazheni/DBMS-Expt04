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
![Screenshot 2024-04-24 184313](https://github.com/Harsayazheni/DBMS-Expt04/assets/118708467/f787636c-0172-440e-bb08-fe3b4ee70a7a)

#### Program
```
SELECT MAX(age) - MIN(age) AS age_difference
FROM employee;
```
#### Output
![Screenshot 2024-04-24 184322](https://github.com/Harsayazheni/DBMS-Expt04/assets/118708467/7324f064-ea6c-4b42-9449-817ca579cc31)

### 7.Write a SQL query to find the number of employees who are having the same age removing the duplicate values.
![Screenshot 2024-04-24 184331](https://github.com/Harsayazheni/DBMS-Expt04/assets/118708467/f1c08458-e0c1-46b6-93ca-43c33872cc6c)

#### Program
```
SELECT COUNT(DISTINCT age) AS COUNT
FROM employee;
```
#### Output
![Screenshot 2024-04-24 184339](https://github.com/Harsayazheni/DBMS-Expt04/assets/118708467/fcb4a60f-153c-4bbf-8d12-b2ddd92ff5bb)

### 8.Write the SQL query that achieves the grouping of data by age, calculates the minimum income for each age group, and includes only those age groups where the minimum income is less than 1,000,000.
![Screenshot 2024-04-24 184347](https://github.com/Harsayazheni/DBMS-Expt04/assets/118708467/8cc19a69-c802-4fcc-956c-d51cdc432c06)

#### Program
```
SELECT age, MIN(income) AS Income
FROM employee
GROUP BY age
HAVING MIN(Income) < 1000000;
```
#### Output
![Screenshot 2024-04-24 184356](https://github.com/Harsayazheni/DBMS-Expt04/assets/118708467/aa4f7219-59f2-4df3-a6d1-606b80ef2529)

### 9.Write the SQL query that accomplishes the grouping of data by joining date (jdate), calculates the average work hours for each date, and excludes dates where the average work hour is not less than 10.
![Screenshot 2024-04-24 184405](https://github.com/Harsayazheni/DBMS-Expt04/assets/118708467/830e3c82-a1e6-4d63-bc9d-1197e2fde446)

#### Program
```SELECT jdate, AVG(workhour) AS "AVG(workhour)"
FROM employee1
GROUP BY jdate
HAVING "AVG(workhour)" < 10;
```
#### Output
![Screenshot 2024-04-24 184414](https://github.com/Harsayazheni/DBMS-Expt04/assets/118708467/ece8b6b9-ed23-4003-832c-6a5fa6dbc874)

### 10.Write the SQL query that achieves the selection of category and calculates the sum of the product of price and category ID as Revenue for each category from the "products" table, and includes only those products where the total revenue is greater than 25.
![Screenshot 2024-04-24 184422](https://github.com/Harsayazheni/DBMS-Expt04/assets/118708467/e2ce4463-53f5-44cb-8292-29ef7f01a9e1)

#### Program
```
SELECT category_id, SUM(price * category_id) AS Revenue
FROM products
GROUP BY category_id
HAVING SUM(price * category_id) > 25;
```
#### Output
![Screenshot 2024-04-24 184430](https://github.com/Harsayazheni/DBMS-Expt04/assets/118708467/d90e0f39-0e96-44b6-90b6-abd9c5f720fe)

## Result
Thus , to develop an application with SQL and programming language using database connectivity is successfully done.
