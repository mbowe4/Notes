# SQL
* Relational Databases:
	* efficient form of storage
* Language designed for accessing databases


## Create a Table: `CREATE TABLE`
* Every table needs a unique identifier (primary key)

```sql
CREATE TABLE grocercies (id INTEGER PRIMARY KEY, name TEXT, quantity INTEGER, aisle INTEGER);
```
**With an auto-generated primary key**:

```sql
CREATE TABLE exercise_logs(id INTEGER PRIMARY KEY AUTOINCREMENT, 
								type TEXT,
								minutes INTEGER,
								calories INTEGER,
								heart_rate INTEGER);
```


## Add data to table: `INSERT INTO`

```sql
INSERT INTO groceries VALUES (1, "Bananas", 4, 2);

// another way to add values:

INSERT INTO exercise_logs(type, minues, calories, heart_rate) VALUES ("biking", 20, 100, 110);
```

## Get values from table: `SELECT`

```sql
SELECT * 
FROM groceries;
```

## Order: `ORDER BY`

```sql
SELECT * 
FROM groceries 
ORDER BY aisle;
```

## Filters and Operators: `WHERE`

```sql
SELECT * 
FROM groceries 
WHERE aisle > 5 
ORDER BY aisle;
```

#### **AND operator**: has precidence over `OR`

```sql
SELECT * 
FROM exercise_logs 
WHERE calories > 50 AND minutes < 30;
```

#### **OR operator**:

```sql
SELECT * 
FROM exercise_logs
WHERE calories > 50 OR heart_rate >100;
```

#### **IN operator**:

* Checks whether a particular values is *in* a list of values

```sql
SELECT * FROM exercise_logs 
WHERE type IN ("biking", "hiking", "tree climbing", "rowing");

// Will return all those activities, is a good alternative to using a bunch of OR operators
```


## HAVING vs. WHERE
* To limit the results of a query based on values of the individual **rows**, use `WHERE`
* To limit the results of a query based on an **aggregate property**, use `HAVING`
* `HAVING` statement always comes after `GROUP BY`, but before `ORDER BY` and `LIMIT`


#### **LIKE operator**:
* Produces and inexact match

```sql
SELECT * 
FROM exercise_logs
WHERE type IN (
	SELECT type FROM drs_favorites WHERE reason LIKE "%cardiovascular%"
);

// The % is a wildcard
// This query matches rows with the word cardiovascular in it

```


## Aggregate Functions
* Can be used to get the average, sum, etc of data in the table

* adding `aisle` after `SELECT` will 

```sql
SELECT aisle, SUM(quantity) 
FROM groceries 
GROUP BY aisle;
```

**how this works behind the scenes:**
1. SQL engine groups rows based on aisle number
2. summed up quantity in each group
3. selected teh first aisle value it saw in each group

**always select the same row you're grouping by so you can get the full picture of the data**

## Subqueries
* Say you wanted to find all activities in your exercise logs that are _also_ in a separate table called `drs_favorites`.
* You can use a subquerie with the `IN` operator to perform this check


```sql
SELECT * 
FROM exercise_logs
WHERE type IN (
	SELECT type FROM drs_favorites
	);
```


## Working with Multiple Tables
* combine two tables called **_orders_** and **_customers_**


```sql
SELECT *           
FROM orders
JOIN customers
	ON orders.customer_id = customers.customer_id;
```

1. Selects all columns from the combined table (could also specify column names)
2. Specifies the first table to look in, **orders**
3. `JOIN` specifies to combine info from **orders** with **customers**
4. How to combine the two tables. ie match **customer_id** from **orders** with **customer_id** from **customers**

#### SELECT: specific columns using join

```sql
SELECT orders.order_id, customers.customer_name
FROM orders
JOIN customers
	ON orders.customer_id = customers.cutomer_id
```












