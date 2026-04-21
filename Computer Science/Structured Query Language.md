---
tags:
  - language
abbreviation: SQL
---
SQL is a language that programmers use to **create, modify and extract data from relational databases**.
It is also used to control user access to that same database.
# Cheat Sheet
```sql
-- Create a new table in the current database
CREATE TABLE weather (
    temp_lo         int,           -- low temperature
    temp_hi         int,           -- high temperature
    prcp            real,          -- precipitation
    date            date
);

-- Insert values into a table
INSERT INTO weather VALUES ('San Francisco', 46, 50, 0.25, '1994-11-27');
-- With the colum names (you can order them freely hen specifiying their names)
INSERT INTO weather (city, temp_lo, temp_hi, prcp, date)
    VALUES ('San Francisco', 43, 57, 0.0, '1994-11-29');

-- Retrieve all columns from a table (query)
SELECT * FROM weather;
-- Retrieve conditionally with WHERE
SELECT * FROM weather
    WHERE city = 'San Francisco' AND prcp > 0.0;
-- Order results first by city, then by temperature
SELECT * FROM weather
    ORDER BY city, temp_lo;
-- Remove duplicate rows with DISTINCT
SELECT DISTINCT city
    FROM weather;

-- JOIN queries allow you to join together two tables to form one result
-- Here, the rows will be all the ones that have the same city in the tables weather and city 
SELECT * FROM weather JOIN cities ON weather.city = city.name;
-- OUTER JOINs allow you to show even rows that didn't have a match
SELECT *
    FROM weather LEFT OUTER JOIN cities ON weather.city = cities.name;
	
-- Aggregate functions compute a single result from multiple input rows
SELECT max(temp_lo) FROM weather;

-- Update all data in a table with UPDATE
UPDATE weather
    SET temp_hi = temp_hi - 2,  temp_lo = temp_lo - 2
    WHERE date > '1994-11-28';
    
-- Remove data from a table with DELETE
DELETE FROM weather WHERE city = 'Hayward';
-- Remove all data from a table (careful!)
DELETE FROM weather;

-- Remove a table
DROP TABLE weather;
```
## Views
Views are **abstractions over a table**, creating a new interface for it that shows only the data you want, how you want it.
**Views can be used in place of tables** almost everywhere in Postgres.
You could even build **views upon views**, if needed.
## Foreign Keys

> [!TODO] Research to be done!!

## Transactions
Transactions are **all-or-nothing operations**.
They are lists of steps to operate on a database, and **if one of them fails, no change is done at all**.
In that sense, transactions are *atomic operations*.
In SQL, you create a transaction by surrounding commands with `BEGIN;` and `COMMIT;`.
# Resources
- [Learn SQL in Y Minutes](https://learnxinyminutes.com/sql/)