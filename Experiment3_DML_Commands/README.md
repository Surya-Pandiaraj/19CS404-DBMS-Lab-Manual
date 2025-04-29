# Experiment 3: DML Commands

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**
--
-- ![image](https://github.com/user-attachments/assets/88ae6e46-bad9-4e73-afec-c705799b49c7)


```sql
-- update sales
set sell_price=sell_price*1.05
where product_id=15 and sale_date='2023-01-31'
```

**Output:**

![image](https://github.com/user-attachments/assets/ff57282c-e288-42d7-ba28-03613565f317)


**Question 2**
---
-- ![image](https://github.com/user-attachments/assets/be44efc6-7c46-4397-96f4-7622de31a069)


```sql
-- update employees
set email='not available',commission_pct=0.55
where department_id=110
```

**Output:**

![image](https://github.com/user-attachments/assets/5eccdc01-4db3-4dcc-ab8b-b0ce950756f2)


**Question 3**
---
-- ![image](https://github.com/user-attachments/assets/8228f35b-abe3-4c92-9f86-465ad42bfcab)


```sql
-- update products
set sell_price=sell_price+(sell_price*10/100)
where supplier_id=6
```

**Output:**

![image](https://github.com/user-attachments/assets/4e2e1c05-e010-4ebf-83b6-48c2b1ed36c5)

**Question 4**
---
-- ![image](https://github.com/user-attachments/assets/d90e7cba-0949-4073-a687-f2ca89848636)


```sql
-- delete from customer
where grade=2 and cust_name like "M%" and payment_amt<=3000
```

**Output:**

![image](https://github.com/user-attachments/assets/29cd4741-3587-400b-bf7d-a78dfc6d1ff1)


**Question 5**
---
-- ![image](https://github.com/user-attachments/assets/687e156d-8257-4ab4-ab74-f0493a6324df)


```sql
-- select lower(ename) as 'EmpName' from emp
```

**Output:**

![image](https://github.com/user-attachments/assets/4fb63dff-03d0-4b7a-a1fd-5ee7024c05a4)


**Question 6**
---
-- ![image](https://github.com/user-attachments/assets/9a44a152-3bcf-4938-a07b-32661011dd08)


```sql
-- select ename,hiredate,julianday('2024-12-31')-julianday(hiredate) as days_worked
from emp
```

**Output:**

![image](https://github.com/user-attachments/assets/26e16e5f-e48a-4f36-9cb1-19d992606146)

**Question 7**
---
-- ![image](https://github.com/user-attachments/assets/2eea4f52-ff49-4b30-b59f-87e5a0befc49)


```sql
-- select product_id,original_price,discount_percentage,tax_rate,
(original_price*(1-discount_percentage))*(1+tax_rate) as final_price
from products
```

**Output:**

![image](https://github.com/user-attachments/assets/9fd022b8-8062-442c-b221-7ab244995187)


**Question 8**
---
-- ![image](https://github.com/user-attachments/assets/c81dabd7-ee1d-4ba4-8d08-8a0fdc661d60)


```sql
-- select customer_id,cust_name,city,grade,salesman_id from customer
where grade>100
```

**Output:**

![image](https://github.com/user-attachments/assets/ff63df33-ab26-4099-8d2d-1ef5feebef5b)


**Question 9**
---
-- ![image](https://github.com/user-attachments/assets/237d401b-ad05-4db4-b293-ee5a9f4cc50b)


```sql
-- delete from doctors
where doctor_id=1
```

**Output:**

![image](https://github.com/user-attachments/assets/2a6a0cfa-8267-4874-87a8-1e0879f4f4d0)


**Question 10**
---
-- ![image](https://github.com/user-attachments/assets/ce8a87f9-00ff-454b-8575-a7ba5fc36a4c)


```sql
-- delete from customer
where cust_country='India' and cust_city <> 'Chennai';

```

**Output:**

![image](https://github.com/user-attachments/assets/adbe7734-1d0a-40d3-b90b-eb6ac02c1f72)


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
