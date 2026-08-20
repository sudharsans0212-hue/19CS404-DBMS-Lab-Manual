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

<img width="850" height="254" alt="image" src="https://github.com/user-attachments/assets/e6bac6dd-4e51-4810-a5da-f24218c66b51" />

```sql
delete from customer
where GRADE=2;
```

**Output:**

<img width="578" height="461" alt="image" src="https://github.com/user-attachments/assets/6c778608-53fc-4fa1-b1e5-544ad6522c29" />

**Question 2**

<img width="725" height="251" alt="image" src="https://github.com/user-attachments/assets/06c53321-90f5-4ea4-8a60-3fb8e29e93f9" />


```sql
delete from surgeries
where surgery_id=3 or surgeon_id=4;
```

**Output:**

<img width="819" height="451" alt="image" src="https://github.com/user-attachments/assets/a004955f-3935-4cb9-984d-1b62dc4eeccd" />

**Question 3**

<img width="842" height="412" alt="image" src="https://github.com/user-attachments/assets/16ac7bcb-b056-4b19-9473-746ab9218adc" />


```sql
update Products
set reorder_lvl=20
where quantity<10 and category='Snacks'
```

**Output:**

<img width="816" height="457" alt="image" src="https://github.com/user-attachments/assets/c2cd7a11-2ce0-4474-842d-6799687d1072" />


**Question 4**

<img width="858" height="320" alt="image" src="https://github.com/user-attachments/assets/4f9f2965-65a5-4e3f-b470-8026bff71051" />

```sql
select customer_id,cust_name,city,grade,salesman_id from customer
where grade is null;
```

**Output:**

<img width="821" height="346" alt="image" src="https://github.com/user-attachments/assets/21dc27a7-f68e-47b9-a69b-bdc0a6aa061b" />

**Question 5**

<img width="845" height="229" alt="image" src="https://github.com/user-attachments/assets/da199295-6abb-4e24-898a-5a45e9360bee" />

```sql
select customer_id,cust_name,city,grade,salesman_id from customer
where grade>100
```

**Output:**

<img width="822" height="357" alt="image" src="https://github.com/user-attachments/assets/bef4effd-9de4-4bb0-8c1f-d99b2fd000ff" />

**Question 6**

<img width="852" height="259" alt="image" src="https://github.com/user-attachments/assets/15934c9e-5811-47b4-8407-3994a77e4658" />

```sql
delete from customer 
where GRADE>=2
```

**Output:**

<img width="557" height="442" alt="image" src="https://github.com/user-attachments/assets/d133ab90-5818-4924-816a-0e012a84606f" />

**Question 7**

<img width="686" height="263" alt="image" src="https://github.com/user-attachments/assets/5f09f4b4-d246-4d43-b2b2-924a38eaace9" />


```sql
select id,value1,
case 
when cast(value1 as integer)%2=0 then 'Even'
else 'Odd'
end as parity
from calculations
```

**Output:**

<img width="597" height="378" alt="image" src="https://github.com/user-attachments/assets/127fc8c9-dd83-40dc-ab43-0609872e73a1" />


**Question 8**

<img width="756" height="286" alt="image" src="https://github.com/user-attachments/assets/5132a2ec-cade-42f2-96c8-ba68163747ce" />

```sql
select product_id,original_price,discount_percentage,
original_price*(1-discount_percentage) as discounted_price
from Products
order by discounted_price desc
limit 3
```

**Output:**

<img width="818" height="231" alt="image" src="https://github.com/user-attachments/assets/c34a7715-8d12-45ce-b180-22b1258066cc" />


**Question 9**

<img width="837" height="228" alt="image" src="https://github.com/user-attachments/assets/1e20c3d2-db38-4e28-a978-85683ca5ed7c" />

```sql
select customer_id,cust_name,city,grade,salesman_id from customer
where city="New York" or grade<=100
```

**Output:**

<img width="820" height="343" alt="image" src="https://github.com/user-attachments/assets/3b24d3e3-e325-4135-8f21-872eb6d429e2" />


**Question 10**

<img width="722" height="494" alt="image" src="https://github.com/user-attachments/assets/2ce9c811-85bb-4086-9b68-cba737c24d98" />

```sql
update SALES
set sell_price=sell_price+3
where product_id in (
select product_id from PRODUCTS
where supplier_id=4
)
```

**Output:**

<img width="814" height="304" alt="image" src="https://github.com/user-attachments/assets/c577337d-2423-4126-9a3c-035c673c21c3" />

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
