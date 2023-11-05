# SQL Revision
This project is dedicated to mastering SQL querying techniques. Here, I'll be sharing valuable insights and practical tips to help enhance SQL skills. This repo is meant for personal development to level up my querying game but feel free to contribute if you like the techniques and pace.

Start by understanding the basics through theoretical courses. SQL Introduction form [W3 Schools](https://www.w3schools.com/sql/sql_intro.asp) and SQL fundamentals from [DataCamp](https://app.datacamp.com/learn/skill-tracks/sql-fundamentals) come in handy. 

#### These cheatsheets from Datacamp provide a quick glance:
**Basics:**
![Alt text](SQLbasicscheatsheet.png)
**Joins:**
![Alt text](SQLjoinscheatsheet.png)

* * * 
#### Practices:

1. To query for a range of records:
```
-- Display all columns of a table where the <column_name> is between 5 and 10
SELECT * 
FROM <Table>
WHERE <column_name> BETWEEN 5 AND 10
```
<br>

2. To query for specific columns:
```
-- Create a list with the required matches to check with the <column_name>
SELECT * 
FROM <table>
WHERE <column> in ('Value1','Value2',...)
```
<br>

3. To query results which match a pattern:
Using `LIKE` and  `NOT LIKE` to check patterns using `%` and `_`
```
SELECT * 
FROM <table>
where <column> LIKE '%d' AND NOT LIKE '_a%'
-- Queries results which end with 'd' and doesn't have 2nd letter as 'a'
```
<br>

4. Condition while Grouping:
`GROUP BY` uses `HAVING` over `WHERE` to add a grouping condition on the query
```
-- Display years which have more than 100 entries
SELECT year
FROM <table>
GROUP BY year
HAVING COUNT(<primary_key>)>100

```
<br>

5. Using a queries result as a condition:
Using `IN` and `NOT IN` to match the query. 
```
SELECT *
FROM <table>
where <column> IN 
    (
        -- Another Query
        SELECT <column2> FROM <table2>
    )
```
<br>

6. Finding the data difference form a data format column:
Use the function `datadiff()`
```
select w2.id
from weather as w1
join weather as w2
where datediff(w2.recordDate, w1.recordDate)=1
-- Finding all the dates from the table 2, where the difference in dates of table 1 is 1
```
<br>

7. To round a column to nearest whole number or specific deminal places:
Use the function `round()`. Specify the number of decimals in the function as a second parameter. 
```
SELECT round(max(<column>,2))
FROM <table>
-- Prints the maximum of a column and rounds it to nearest value to 2 decimal places. 
```
<br>

8. 