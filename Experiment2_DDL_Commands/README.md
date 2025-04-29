# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**
--
-- ![image](https://github.com/user-attachments/assets/bc6f6af1-fbb9-435f-89de-d52157dd57f5)


```sql
insert into Products(Name,Category,Price,Stock) values('Smartphone','Electronics',800,150),('Headphones','Accessories',200,300);
```

**Output:**

![image](https://github.com/user-attachments/assets/5b1ca3a5-04a7-4b9f-b4cb-f78193467890)


**Question 2**
---
-- ![image](https://github.com/user-attachments/assets/3a42018e-6f92-4ca1-a71f-196d95c05f1d)


```sql
-- create table item(
item_id TEXT primary key,
item_desc TEXT not null,
rate INTEGER not null,
icom_id TEXT(4),
foreign key (icom_id) references company (com_id) on update set null on delete set null);
```

**Output:**

![image](https://github.com/user-attachments/assets/415862ba-5585-4250-9334-f33432f9ba32)


**Question 3**
---
-- ![image](https://github.com/user-attachments/assets/f534be86-f09f-4fc5-84c7-7636480ff637)


```sql
-- create table Products(
ProductID int primary key,
ProductName text not null,
Price real,
Stock int,
check(Price>0),
check(Stock>=0));
```

**Output:**

![image](https://github.com/user-attachments/assets/41a9b76e-11d8-4e02-932e-4a80e1a056cc)


**Question 4**
---
-- ![image](https://github.com/user-attachments/assets/ed864134-23f6-418d-b337-243672210a2a)



```sql
create table Attendance(
AttendanceID INTEGER primary key,
EmployeeID INTEGER,
AttendanceDate DATE,
Status TEXT,
check(Status in ('Present','Absent','Leave')),
foreign key(EmployeeID) references Employees(EmployeeID));
```

**Output:**

![image](https://github.com/user-attachments/assets/c11c1746-c8fe-486a-8534-363d0de39d38)


**Question 5**
---
-- ![image](https://github.com/user-attachments/assets/4aa9e9db-66f1-4c8c-a5eb-00a95cab7e38)


```sql
-- insert into Products(ProductID,Name,Category,Price,Stock)
values(101,'Laptop','Electronics',1500,50);
```

**Output:**

![image](https://github.com/user-attachments/assets/48253236-69d4-42ef-b69e-8a1433ce0941)


**Question 6**
---
-- ![image](https://github.com/user-attachments/assets/d18b1840-dac9-4a72-9609-513af975f2b3)


```sql
-- alter table Student_details
add column ParentsNumber number;
alter table Student_details
add column Adhar_Number number;
```

**Output:**

![image](https://github.com/user-attachments/assets/3a7d27ca-e014-40a1-853e-4de06457b1b1)


**Question 7**
---
-- ![image](https://github.com/user-attachments/assets/04a4d3cc-c44a-4129-8687-24e203d59dcb)


```sql
-- create table Invoices(
InvoiceID int primary key,
InvoiceDate date,
Amount real,
DueDate date,
OrderID int,
check (amount>0),
check (DueDate>InvoiceDate),
foreign key (OrderID)references Orders(OrderID));
```

**Output:**

![image](https://github.com/user-attachments/assets/0ea83df4-6b5e-4a85-a384-24bb8541f877)


**Question 8**
---
-- ![image](https://github.com/user-attachments/assets/56f83ce6-c560-410d-bce1-285ce94a4479)


```sql
-- create table Customers(
CustomerID INTEGER,
Name TEXT,
Email TEXT,
JoinDate DATETIME);
```

**Output:**

![image](https://github.com/user-attachments/assets/6dba59b3-bca1-4f06-83ae-91b7895823f1)

**Question 9**
---
-- ![image](https://github.com/user-attachments/assets/6b02a17f-22d7-4ee7-a149-ba6654800a58)

```sql
-- insert into Student_details select * from Archived_students;
```

**Output:**

![image](https://github.com/user-attachments/assets/8475d606-103c-4772-b897-a3d1ba82756f)




## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
