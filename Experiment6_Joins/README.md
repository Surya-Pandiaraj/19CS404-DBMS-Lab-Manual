# Experiment 6: Joins

## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

**Question 1**
--
-- ![image](https://github.com/user-attachments/assets/3bece252-bc92-435e-b88d-bdbdc103e445)


```sql
-- SELECT 
    c.cust_name,
    o.ord_no,
    o.ord_date,
    o.purch_amt
FROM 
    customer c
LEFT JOIN 
    orders o
ON 
    c.customer_id = o.customer_id;

```

**Output:**

![image](https://github.com/user-attachments/assets/5bca2f2b-23a3-499d-b471-74e68bf7b270)


**Question 2**
---
-- ![image](https://github.com/user-attachments/assets/c446f0b8-24db-4e7d-9c0b-b133122a8e64)


```sql
-- SELECT 
    c.cust_name AS "Customer Name",
    c.city AS "city",
    s.name AS "Salesman",
    s.commission AS "commission"
FROM 
    customer c
JOIN 
    salesman s
ON 
    c.salesman_id = s.salesman_id
WHERE 
    s.commission > 0.12;

```

**Output:**

![image](https://github.com/user-attachments/assets/e354c465-d821-47fc-aac7-a8070136ad1f)


**Question 3**
---
-- ![image](https://github.com/user-attachments/assets/7c15df70-30a0-4ea7-a560-529fab09b855)


```sql
-- SELECT 
    c.cust_name,
    s.commission
FROM 
    customer c
LEFT JOIN 
    salesman s
ON 
    c.salesman_id = s.salesman_id;

```

**Output:**

![image](https://github.com/user-attachments/assets/d3cf6d72-60a9-4eca-a435-61eddef22ae9)


**Question 4**
---
-- ![image](https://github.com/user-attachments/assets/eabc6f42-7e18-4a2f-b070-fd1fd295fa34)


```sql
-- SELECT 
    c.cust_name AS "cust_name",
    c.city AS "city",
    c.grade AS "grade",
    s.name AS "Salesman",
    s.city AS "city"
FROM 
    customer c
JOIN 
    salesman s
ON 
    c.salesman_id = s.salesman_id
WHERE 
    c.grade < 300
ORDER BY 
    c.customer_id ASC;

```

**Output:**

![image](https://github.com/user-attachments/assets/e844f653-a1e2-4553-8088-a978064e9fba)


**Question 5**
---
-- ![image](https://github.com/user-attachments/assets/3105085a-8a6a-4c5b-8acd-4320f0e548bd)


```sql
-- SELECT 
    p.first_name AS patient_name,
    a.*
FROM 
    patients p
INNER JOIN 
    appointments a
ON 
    p.patient_id = a.patient_id;
```

**Output:**

![image](https://github.com/user-attachments/assets/47273379-7d86-4ce1-9c78-8abcd67e6e97)


**Question 6**
---
-- ![image](https://github.com/user-attachments/assets/73fc3862-fdee-4cb6-9d3d-6c42fb620595)


```sql
-- SELECT 
    p.first_name AS patient_name
FROM 
    patients p
INNER JOIN 
    doctors d
ON 
    p.doctor_id = d.doctor_id
WHERE 
    d.first_name = 'Emily'
    AND d.last_name = 'Johnson'
    AND p.discharge_date IS NOT NULL;

```

**Output:**

![image](https://github.com/user-attachments/assets/3fd50068-e10f-407e-9c16-b6451c7fb991)

**Question 7**
---
-- ![image](https://github.com/user-attachments/assets/3d4c8702-430f-41c1-b5da-ad4b1c98a79c)


```sql
-- SELECT 
    n.*, 
    d.department_name
FROM 
    nurses n
INNER JOIN 
    departments d
ON 
    n.department_id = d.department_id;

```

**Output:**

![image](https://github.com/user-attachments/assets/c199ec43-85f9-4566-be93-23fa8c233356)


**Question 8**
---
-- ![image](https://github.com/user-attachments/assets/84084753-30e8-41ae-b7a8-d7112f13a42f)

```sql
-- SELECT 
    c.cust_name AS "cust_name",
    c.city AS "city",
    o.ord_no AS "ord_no",
    o.ord_date AS "ord_date",
    o.purch_amt AS "Order Amount"
FROM 
    customer c
LEFT JOIN 
    orders o
ON 
    c.customer_id = o.customer_id
ORDER BY 
    o.ord_date ASC;

```

**Output:**

![image](https://github.com/user-attachments/assets/544d779e-3d45-4bf9-b724-f1fc0dc6a247)


**Question 9**
---
-- ![image](https://github.com/user-attachments/assets/f528c471-4316-4880-8a4c-d6aa1c0b7966)


```sql
-- SELECT 
    c.cust_name AS "Customer Name",
    c.city AS "city",
    s.name AS "Salesman",
    s.commission AS "commission"
FROM 
    customer c
INNER JOIN 
    salesman s
ON 
    c.salesman_id = s.salesman_id;

```

**Output:**

![image](https://github.com/user-attachments/assets/1fcb833c-8e83-4c87-bbae-179ab5d0709e)


## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
