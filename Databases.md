# Databases
### Relational Databases
- relations -> rows
- fields -> columns

### SQL
- language used with relational databases

### CLAUSES
- **Create Table:** define table attributes & create table
- Can be modified later with **Alter Table**

```sql
CREATE TABLE cars (
	id INT NOT NULL AUTO_INCREMENT,
	make VARCHAR(255) NOT NULL,
	model VARCHAR(255) NOT NULL,
	PRIMARY KEY(id),
	CONSTRAINT unique_make_model_year UNIQUE (make, model, year)
);
```   

- **SELECT:** extracts data
	- Used with `DISTINCT` (unique values), `FROM`, `WHERE` (filter using operators), 

```sql
SELECT CustomerName, City FROM Customers;

SELECT DISTINCT column1, column2, ... FROM table_name;
```

- **UPDATE:** modifies existing records 
	- Be sure to use a `WHERE` clause or else _all_ records in the table will be updated

```sql
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```

- **DELETE:** deletes data 
- **INSERT INTO:** inserts new data
	- if a field in the table is optional it is possible to insert/update a record w/out adding a value to this field. Results in *NULL* value

```sql
INSERT INTO table_name (column1, column2, column3, ...)
VALUES (value1, value2, value3, ...);
```

- **CREATE DATABASE:** creates new database
- **ALTER DATABASE:** modifies database
- **CREATE TABLE:** creates new table
- **ALTER TABLE:** modifies a table
- **DROP TABLE:** deletes a table
- **CREATE INDEX:** creates an index (search key)
- **DROP INDEX:** deletes an index

#### Functions:
- **MIN(), MAX()**
- **COUNT(), AVG(), SUM()**

####

   
### ORDER:
```sql
SELECT column_names(s)
FROM table_name
WHERE condition
GROUP BY column_name(s)
HAVING condition
ORDER BY column_name(s);
```

#### Resources:
- W3 schools
- Code School
- H2 Reference
- SQL Zoo