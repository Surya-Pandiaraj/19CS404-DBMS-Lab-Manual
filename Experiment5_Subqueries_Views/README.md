# Experiment 5: Subqueries and Views

## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```

**Question 1**
--
-- ![image](https://github.com/user-attachments/assets/ccb31d16-5294-419a-9bce-70b079c19ae9)


```sql
-- SELECT ord_no,purch_amt,ord_date,customer_id,orders.salesman_id
FROM orders
JOIN salesman ON orders.salesman_id = salesman.salesman_id
WHERE 
    salesman.name = 'Paul Adam';

```

**Output:**

![image](https://github.com/user-attachments/assets/58b04ce6-8066-4b51-b79d-c2dd977b0617)


**Question 2**
---
-- ![image](https://github.com/user-attachments/assets/a1f14381-e650-4e6b-bf2b-af7332df2a9f)


```sql
-- SELECT ord_no, purch_amt, ord_date, customer_id, salesman_id
FROM orders
WHERE 
    purch_amt > (SELECT AVG(purch_amt)
        FROM orders
        WHERE ord_date = '2012-10-10');

```

**Output:**

![image](https://github.com/user-attachments/assets/0337dd2d-98bd-4e62-85f2-24d8e998197e)


**Question 3**
---
-- ![image](https://github.com/user-attachments/assets/0d8ca6bf-718d-444d-a3ad-15842b75bc78)


```sql
-- SELECT *
FROM CUSTOMERS
WHERE SALARY > 4500;


```

**Output:**

![image](https://github.com/user-attachments/assets/677ec5be-11d6-4a01-9cec-1c47fa0fc8d3)


**Question 4**
---
-- ![image](https://github.com/user-attachments/assets/64873da8-32bf-4fac-971f-cf589aca9ecc)


```sql
-- SELECT g.student_name, g.grade
FROM grades g
WHERE g.grade = (
    SELECT MIN(grade)
    FROM grades
    WHERE subject = g.subject
)
ORDER BY  g.grade,g.subject;

```

**Output:**

![image](https://github.com/user-attachments/assets/7f89be22-8dc4-4171-8f67-b3fc835985a5)


**Question 5**
---
-- ![image](https://github.com/user-attachments/assets/d4fb8b24-e8ab-4fd2-b5a0-b19c52216e1a)


```sql
-- SELECT s.salesman_id, s.name
FROM salesman s
JOIN customer c ON s.salesman_id = c.salesman_id
GROUP BY s.salesman_id, s.name
HAVING COUNT(c.customer_id) > 1;

```

**Output:**

![image](https://github.com/user-attachments/assets/01e686dd-a2e5-4cac-a31c-2c80a02c0e77)


**Question 6**
---
-- ![image](https://github.com/user-attachments/assets/f04d4720-644c-4745-9458-4abb15304b12)


```sql
-- SELECT e.id, e.name, e.age,e.city,e.income
FROM employee e
WHERE e.age < (SELECT AVG(age) 
               FROM employee 
               WHERE income > 1000000);

```

**Output:**

![image](https://github.com/user-attachments/assets/fb43bb62-919e-44f9-87e9-3eaffda25ff9)


**Question 7**
---
-- ![image](https://github.com/user-attachments/assets/79231dd7-0cff-45bd-aebc-5497005b8601)


```sql
-- SELECT c.id, c.name, c.city,c.email,c.phone
FROM customer c
WHERE c.city != (SELECT city FROM customer WHERE id = (SELECT MAX(id) FROM customer));

```

**Output:**

![image](https://github.com/user-attachments/assets/406bd13b-1bee-4fb8-bdf3-ce727ddc57ba)


## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
