
1. sharding


2. DBMS => database management system is based on a relational model of data that is
stored in database in separate tables. can be queried using Structured Query language.

3. when to use sql instead of no sql?
=> 1. when working with complex queries and reports.
   2. you have a high transaction application
   3. You have to ensure ACID compliance (Atomicity, Consistency, Isolation, Durability)
   4. You dont anticipate lot of changes and growth.


3. In one to many  1 ---* relation there is a foreign key of first table in second table which is implicit.

4. Use enumeration as a separate table wherever necessary

5. many to many is weak to weak relationship ----- create another table in between to create one to many instead.

6. Generalisation is inheritance "is a " relation

7. Aggregation is "contains or part of " relation. ex: page contains widgets

8. Composition is "composed of" relation. ex: page is composed of widgets.

9. if there is one to one relation primary key of main table is sufficient to denote the second table as well

10. Distinct returns distinct column values of a column
    Like in where clause is used for pattern matching '_' matches one whereas '%' matches man.
    Case statement is written before from in select.
    || is used to concatenate--> we can also concatenate an integer to string.

11. Joins
  => Join, inner join-> returns matched throws
     Left join, left outer join-> returns all columns of left table regardless of match (unmatched in empty) (if any case)
     Right join, right outer join-> returns all columns from right table regardless of match (unmatched is empty)
     Full join, full outer join -> returns all columns from both tables regardless of match.

12.  BETWEEN is used in where clause to select the range . similarly NOT BETWEEN
      IN allows multiple values in where clause

13. SQL constraints-> NOT NULL, PRIMARY KEY, FOREGIN KEY, UNIQUE, CHECK, DEFAULT

14. UNION combines results of two or more Select statements. Only distinct values are returned.
    UNION ALL returns all even if it is not distinct.

15. Order by  sorts the columns  defualt asc || desc for descending

16. Group by clause works with aggregate functions.
    SELECT column_name,
    aggregate_function(other_columns)
    FROM table_name
    WHERE column_name operator value
    GROUP BY column_name    
    Cant have aggregation functions in where clause because records have not yet been grouped.
    evaluated after where, before select

17. HAVING clause allows WHERE to use aggregate functions.
    SELECT Customer, SUM(OrderPrice) FROM Orders
    GROUP BY Customer
    HAVING SUM(OrderPrice) < 2000




#### Questions asked:

  1. How do you scale a database? Sql or No-SQL
  2. Difference between SQL and No SQL databases..
