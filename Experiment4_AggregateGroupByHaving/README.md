# Experiment 4: Aggregate Functions, Group By and Having Clause

## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**
--
-- ![image](https://github.com/user-attachments/assets/46da796a-cdec-455e-8542-3f029a79664f)


```sql
-- select doctorid,count(*) as TotalRecords
from medicalrecords
group by doctorid
```

**Output:**

![image](https://github.com/user-attachments/assets/b6ec8f83-0a3a-483c-b4d7-bb9067008e86)


**Question 2**
---
-- ![image](https://github.com/user-attachments/assets/08dc78ac-f1bc-4146-994a-4365dc928b8c)


```sql
-- select doctorid,count(*) as TotalAppointments
from Appointments
group by doctorid
```

**Output:**

![image](https://github.com/user-attachments/assets/ba2dfc42-c858-40a9-aa0c-7eece7f1aedb)


**Question 3**
---
-- ![image](https://github.com/user-attachments/assets/fe51e5dd-1d2d-4e24-b21f-0923b66263d9)


```sql
-- select strftime('%Y',ValidityPeriod) as ValidityYear,count(*) as TotalPatients
from Insurance
group by ValidityPeriod
```

**Output:**

![image](https://github.com/user-attachments/assets/71bf0a5a-b5d9-453d-9f8d-1bd32c34a6c8)


**Question 4**
---
-- ![image](https://github.com/user-attachments/assets/7fd7ada1-5e70-4400-a400-e7ff2ed283fd)


```sql
-- select name,max(income)
from employee
where city='California'
```

**Output:**

![image](https://github.com/user-attachments/assets/7a624b09-bb89-4b88-b6b0-96e3ac6edeb2)


**Question 5**
---
-- ![image](https://github.com/user-attachments/assets/0a12c4c7-d032-4b69-aa51-bc6f067a6445)


```sql
-- select sum(inventory) as total
from fruits
where unit ='LB'
```

**Output:**

![image](https://github.com/user-attachments/assets/ae9ba880-5395-4158-a1d4-cc1873e6aa81)


**Question 6**
---
-- ![image](https://github.com/user-attachments/assets/d42c42ca-6d87-4022-8307-74e5ac1eca40)

```sql
-- select avg(length(email)) as avg_email_length_below_30
from customer
where city='Mumbai'
```

**Output:**

![image](https://github.com/user-attachments/assets/dfa23a56-c512-4f0d-ab50-7ecead08046b)


**Question 7**
---
-- ![image](https://github.com/user-attachments/assets/1b702cf2-004e-4f71-b49b-9bde1bbf7654)


```sql
-- select count(distinct city) as unique_cities
from customer
```

**Output:**

![image](https://github.com/user-attachments/assets/7dfcca13-9407-4473-92dd-c8bae65d6384)


**Question 8**
---
-- ![image](https://github.com/user-attachments/assets/50a85310-0379-436f-a9d9-4fa502dca66e)


```sql
-- select jdate,AVG(workhour)
from employee1
group by jdate
having avg(workhour)<=10
```

**Output:**

![image](https://github.com/user-attachments/assets/2ede931e-4fb8-410a-99a6-a356344d43c0)


**Question 9**
---
-- ![image](https://github.com/user-attachments/assets/9bcb3618-28c1-4386-987a-33ec499a0ed3)


```sql
-- select (age/5)*5 as age_group, AVG(age)
from customer1
group by(age/5)*5
having avg(age)<24
```

**Output:**

![image](https://github.com/user-attachments/assets/51492f4a-c4d5-481c-a70f-af7bf07c52dc)


**Question 10**
---
-- ![image](https://github.com/user-attachments/assets/e9182f42-3173-4eff-9902-5cc15a04eba3)


```sql
-- select category_id,sum(price) as Total_Cost
from products
group by category_id
having sum(price)>50
```

**Output:**

![image](https://github.com/user-attachments/assets/9c4e8afc-1857-461f-a9a6-ecfe83fe29b3)



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
