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

<img width="851" height="358" alt="image" src="https://github.com/user-attachments/assets/42b63c7e-636a-496e-8670-8cc2a7377a51" />

```sql
alter table Student_details add MobileNumber NUMBER;
alter table Student_details add Address VARCHAR(100);
```

**Output:**

<img width="818" height="300" alt="image" src="https://github.com/user-attachments/assets/072f0b6f-3322-46e0-b536-634e034245bb" />

**Question 2**

<img width="729" height="392" alt="image" src="https://github.com/user-attachments/assets/fa3a3b9c-3a0b-4c09-8bb4-286c78c1b43c" />

```sql
insert into Student_details select * from Archived_students;
```

**Output:**

<img width="816" height="225" alt="image" src="https://github.com/user-attachments/assets/71c3d6cc-c12d-4ec2-ad8f-794534c6afc4" />

**Question 3**

<img width="851" height="278" alt="image" src="https://github.com/user-attachments/assets/8350c246-272d-42d5-a172-25d4a87792ad" />

```sql
create table Orders(
OrderID INTEGER primary key,
OrderDate DATE not null,
CustomerID INTEGER,
foreign key (CustomerID) references Customers(CustomerID)
);
```

**Output:**

<img width="855" height="244" alt="image" src="https://github.com/user-attachments/assets/5eea0085-7b03-4ba4-8058-90f8450b07f2" />

**Question 4**

<img width="859" height="226" alt="image" src="https://github.com/user-attachments/assets/67ec6902-878f-49c2-849a-cde1a5377e68" />

```sql
insert into Student_details (RollNo,Name,Gender,Subject,Marks) values (201,"David Lee","M","Physics",92);
```

**Output:**

<img width="855" height="200" alt="image" src="https://github.com/user-attachments/assets/127c49e1-1e79-4402-b830-e9f9f8f61836" />

**Question 5**

<img width="826" height="380" alt="image" src="https://github.com/user-attachments/assets/54edcdb6-29c7-4400-8338-22b792dcc5f3" />

```sql
create table customers(
CustomerID INTEGER,
Name TEXT,
Email TEXT,
JoinDate DATETIME
);
```

**Output:**

<img width="850" height="336" alt="image" src="https://github.com/user-attachments/assets/41905714-f42b-4a97-9158-cff89a7a7486" />

**Question 6**

<img width="803" height="298" alt="image" src="https://github.com/user-attachments/assets/3cce116f-6407-49a4-a2f7-3c5428d1d3e0" />

```sql
insert into Books select * from Out_of_print_books;
```

**Output:**

<img width="855" height="245" alt="image" src="https://github.com/user-attachments/assets/86c99287-b1f4-47ab-955d-345e1128d09f" />

**Question 7**

<img width="771" height="248" alt="image" src="https://github.com/user-attachments/assets/d3af3d5a-e865-43b2-b1a9-becb252069db" />

```sql
alter table employee add designation varchar(50);
```

**Output:**

<img width="858" height="246" alt="image" src="https://github.com/user-attachments/assets/fceb6b54-3650-4923-9289-618109eef839" />

**Question 8**

<img width="850" height="298" alt="image" src="https://github.com/user-attachments/assets/01d18f85-91f0-4873-ab7c-696e9e2fd35d" />

```sql
Create table ProjectAssignments(
AssignmentID INTEGER primary key,
EmployeeID INTEGER, 
ProjectID INTEGER,
AssignmentDate DATE NOT NULL,
foreign key (EmployeeID) references Employees(EmployeeID),
foreign key (ProjectID) references Projects(ProjectID)
);
```

**Output:**

<img width="811" height="224" alt="image" src="https://github.com/user-attachments/assets/6fc75b59-6f84-43c0-8151-e4f96e7af680" />

**Question 9**

<img width="863" height="326" alt="image" src="https://github.com/user-attachments/assets/d09344cc-19aa-4f5c-bdf4-f6f2add25eb0" />

```sql
create table Employees(
EmployeeID INTEGER primary key,
FirstName TEXT NOT NULL,
LastName TEXT NOT NULL,
Email varchar(50) unique,
Salary decimal(10,2) check (Salary>0),
DepartmentID integer,
foreign key (DepartmentID) references Departments(DepartmentID)
)
```

**Output:**

<img width="814" height="335" alt="image" src="https://github.com/user-attachments/assets/f9f2cf25-81c4-49fb-924d-b0cad5e3649f" />

**Question 10**

<img width="848" height="296" alt="image" src="https://github.com/user-attachments/assets/d072861d-742e-4621-bef1-d7fbd9399f93" />

```sql
create table Products(
ProductID INTEGER primary key,
ProductName TEXT UNIQUE NOT NULL,
Price REAL check(Price>0),
StockQuantity INTEGER check(StockQuantity>0)
);
```

**Output:**

<img width="815" height="225" alt="image" src="https://github.com/user-attachments/assets/5e6363bb-07ce-46f8-9fa1-1b1198901308" />


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
