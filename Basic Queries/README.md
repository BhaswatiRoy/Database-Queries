1. `SHOW DATABASES` - show all databases 
2. `CREATE TABLE mathtest (d1 DECIMAL(4,2), d2 DECIMAL (4,2), f1 FLOAT, f2 FLOAT)` - create a database with name "mathtest" containing 4 columns d1,d2 of decimal values containing max 4 digits with 2 digits after decimal point and f1,f2 float values
3. `INSERT INTO mathtest VALUES (1.5, 1.7,2.5,2.7)` - insert the 4 values into 4 columns d1,d2,f1,f2
4. `SELECT d1+d2 FROM mathtest` - select d1,d2 and add them up to display
5. `CREATE DATABASE dbname` - creates a new database/schema with name dbname
6. `DROP TABLE 'schemaname'.'tbname'` - drops the table with name 'tbname' from the schema 'schemaname' //this can be manually done also
7. `CREATE TABLE musictable (id INT PRIMARY KEY NOT NULL AUTO_INCREMENT, title VARCHAR(100), genre VARCHAR(20), release_year INT);` - create tables with given column names and details under each column name
8. `ALTER TABLE tbname` - specifies the table that needs to be altered/modified
9. `ADD COLUMN columnname dtype` - adds/creates a column with name 'columnname' and data type 'dtype'
10. `RENAME COLUMN oldname TO newname` - changes the column name from 'oldname' to 'newname'
11. `SELECT * FROM schemaname.tbname` - selects all rows & columns from the schema with name 'schemaname' and table with name 'tablename'
12. `SELECT c1,c2 FROM schemaname.tbname` - selects the columns with column names c1 & c2 from the schema with name 'schemaname' and table with name 'tablename'
13. `SELECT * FROM tbname LIMIT X` - selects top X rows from the table with name 'tbname'
14. `SELECT * FROM tbname LIMIT X,Y` - selects rows from X to Y numbered from the table with name 'tbname'
15. `SELECT c1 AS 'C1' FROM tbname` - shows column c1 with column name displayed as C1 
16. `SELECT * FROM tbname ORDER BY c1 ASC/DESC` - shows all rows ordering the entire table on basis of column c1 in ascending order(ASC) or in descending order(DESC)
17. `SELECT * FROM tbname WHERE id <= X` - shows all the rows where id <= X in which X can be any value
18. `SELECT * FROM tbname WHERE c1 LIKE 'ABC' - shows all the rows where the value in the column with column name c1 values are 'ABC'
19. `SELECT * FROM tbname WHERE c1 NOT LIKE 'ABC' - shows all the rows where the value in the column with column name c1 values are 'ABC'
20. `SELECT * FROM tbnam WHERE c1 LIKE 'ABC' AND c2>X` - shows all rows that satisfy both conditions of AND operation
21. `SELECT * FROM tbname WHERE c1 LIKE 'ABC' OR c2>X` - shows all rows that satisfy any one conditions of OR operation
22. `SELECT * FROM tbname WHERE LENGTH(c1)>10` - shows all rows that has length of characters of the value in column 'c1' >10
23. `SELECT c1 AS 'C1', IF (c2>6,'Good','Bad') AS 'C2' FROM tbname` - shows all c1 values and replaces c2 value with 'Good' if >6 otherwise replaces c2 value with 'Bad'. It also replaces the column name 'c1' with 'C1' & column name 'c2' with 'C2'
24. `SELECT c1 AS 'C1', CASE WHEN c2<5 THEN 'Bad' WHEN c2<8 THEN 'DESCENT' ELSE 'GOOD' END AS 'c2' FROM tbname` - does the same operation as last command only difference is here CASE is used
25. `INSERT INTO tbname (c1,c2) VALUES ('value1','value2')` - insert the values 'value1' & 'value2' into columns 'c1' & 'c2'. We can also add multiple values at a time
26. `UPDATE tbname SET c1 = 'Y' WHERE c1='X'`- sets column c1 value to 'Y' from 'X'. This is only possible in a non safe environment in MySQL as MySQL Workbench has safe environment by default so we need to change it before we use this.
27. `DELETE FROM tbname WHERE c1 < x` - deletes the values of the column which has 
28. `SELECT tbname1.c1 , tbname2.c3 FROM tbname1 INNER JOIN tbname2 ON tbname1.id=tbname2.id` - Inner join 2 tables on basis of id primary key column
29. `SELECT tbname1.c1 , tbname2.c3 , tbname3.c5 FROM tbname1 INNER JOIN tbname2 ON tbname1.id=tbname2.id JOIN tbname2 ON tbname1.id=tbname3.id` - Inner join 3 tables on basis of id primary key column
30. 
