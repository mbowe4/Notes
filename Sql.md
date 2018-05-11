# SQL


```sql
Select * 
From employees
Where employees.name Like 'A%'
```

### Indexing
* makes things easier to find and improves speed of data retrieval

### Relationships
* **one to one**: one item in table A has one item in Table B
* **one to many**: guitar to guitar strings
* **many to one**: one time in table a has many items in b, vice versa


### MYSQL
* Relational Database Managment system

### Creating a Scheme with Tables
* Schema creation: `CREATE SCHEMA zipcode`
* Scheme: collection of tables in a database
	* allow you to manage multiple applications in the same database
* _VARCHAR_: varying number of characters up to the number specified, faster if under 255 character limit
* _TINYTEXT_: String field with ~255 characters
* _UNSIGNED_: Positive number


**Create a table**:

```sql
CREATE TABLE zipcode.teachers
(
	id INTEGER PRIMARY KEY NOT NULL AUTO_INCREMENT,
	name VARCHAR(50) NOT NULL,
	specialty ENUM('FRONT END', 'MIDDLE TIER', 'DATA TIER')

);
CREATE UNIQUE INDEX teachers_id_uindex ON zipcode.teachers (id);
```

#### Inserts
* 3 parts:
	1. reference to the table you want to insert into
	2. columns you want to fill
	3. values to fill those columns
* `INSERT INTO zipcode.teachers (first_name, last_name, specialty)
    VALUES ('John', 'Smith', 'FRONT END');`

