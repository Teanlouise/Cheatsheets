# SQL - CHEATSHEET

## TABLE

**STATEMENT:** A command, ends with ;

**CLAUSE:** a task of command

**PARAMETER:** list of columns/data types/values passed as an argument to a clause

**KEYS**
- PRIMARY KEY: not null, unique, only 1 column per table can be pk
- FOREIGN KEY: referencing primary key from another table 

**CREATE TABLE**
```
CREATE TABLE name (
    id INTEGER PRIMARY KEY
    name TEXT DEFAULT 'text'    
);
```

**INSERT INTO** 
```
INSERT INTO table (id, name, age)
VALUES (1, 'name', 22);
```
* Note: Date - 'YYYY-MM-DD'

**ALTER TABLE**
```
ALTER TABLE table
ADD COLUMN name TEXT;
```

**UPDATE**
```
UPDATE
SET COLUMN = 'name'
WHERE column2 = #;
```

**DELETE FROM**
```
DELETE FROM table
WHERE column IS NULL;
```

**CONSTRAINTS**
- PRIMARY KEY
- UNIQUE
- NOT NULL
- DEFAULT


## BASICS

**SELECT**
```
SELECT DISTINCT name AS 'new name'
FROM table
```
- `DISTINCT`: no duplicates
- `AS`: rename column to 'new name'

**WHERE**
```
SELECT * 
FROM table
WHERE name ='name'
```
(Return all rows the name 'name')
- `IS NULL`: Column is empty
- `IS NOT NULL`: Column has value

**LIKE**
```
SELECT * 
FROM table
WHERE name LIKE '%man%'
```
(Return all names containing 'man')
- `n_me` : _ is wildcard
- `'a%'`: begins with a (not case sensitive)
- `'%a'`: ends with a

**BETWEEN**
```
SELECT * 
FROM table
WHERE name BETWEEN 'A' AND 'C';
```
(Return: All names starting with A and B)
- Note: Numbers = inclusive range, text = exclusive


**ORDER BY**
```
SELECT name, age
FROM table
ORDER BY age;
```
- `DESC`: High to low
- `ASC`: Low to high (default)
- Note: Can also access by column number in select eg. `ORDER BY 2`

**CASE**
```
SELECT name,
    CASE
        WHEN rating > 1 THEN 'text
        ELSE 'text2'
    END AS 'name2
FROM table;
```

**STRFRAME**
```
strframe(format, column)
```
- Example: column = 'YYYY-MM-DD HH:MM:SS'
return %Y $m $d %H %M %S


## AGGREGATES

**AGGREGATES**: calcs on multiples rows of tables

```
SELECT COUNT(*)
FROM table;
```
- `COUNT(column)`: ount how many rows are in column
- `SUM(column)`: Add total of column
- `MAX(column)`: Only show max value of column
- `MIN(column)`: Only show min value of column
- `AVG(column)`: Get the average of column
- `ROUND(column, decimals)`: Round column by number of decimals

**GROUP BY**
```
SELECT name
FROM table
GROUP BY name;
```
* Note: Must have groupby column in select, 
* Note: Can also access by number eg. `GROUP BY 1` 

**HAVING**

```
SELECT name, age
FROM table
GROUP BY age
HAVING age > 2;
```
- Note: Similar to WHERE but to filter groups

## JOINS

**INNER JOIN**
```
SELECT * 
FROM table1
JOIN table2 ON table1.id = table2.id;
```
- Note: Only rows matching ON

**LEFT JOIN**
```
SELECT *
FROM table1
LEFT JOIN table2 ON table1.id = table2.id;
```
- Note: Keep all rows from table1, even if no match with table2, NULL if no match

**CROSS JOIN**
```
SELECT name, COUNT(*)
FROM table 1
CROSS JOIN table2
WHERE start <= month AND end >= month
GROUP BY month;
```
(Return number of subscribers for each month)
- Note: join all rows with one another, produce all possible combinations, 
used to compare values

**UNION**
```
SELECT *
FROM table1
UNION
SELECT *
FROM table2
```
- Note: stack datasets, must have same # of columns and same datatyypes in same 
order, no duplicates
- `UNION ALL`: same but includes duplicates

**INTERSECT**
```
SELECT name
FROM table1
INTERSECT
SELECT name
FROM table2
```
- Note: Only returns from table1 if identical to table 2

**EXCEPT**
```
SELECT name
FROM table1
EXCEPT
SELECT name
FROM table2
```
- Note: distinct from table1 and not in table2 

**WITH**
```
WITH previous_results AS (
        SELECT *
        FROM table1
        WHERE......
)
SELECT *
FROM previous_results
JOIN table2 ON table2.id = previous_results.id;
```
- Note: previous_results is a temporary table that only used in following query




# ANALYSIS
- Churn Rate: % of subscribers to monthly service who have cancelled
- Retention Rate: Opposite i.e. 100 - Churn rate

**MACHINE LEARNING**
- Computer acting like humans
- Supervised: data labelled, predict output from input eg. learn what is fradulent from past
- Unsupervised: unlabeled, recognise inherent structure of data eg. group based on patterns