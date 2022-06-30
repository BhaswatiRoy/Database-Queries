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
20. `SELECT * FROM movies_basic WHERE c1 LIKE 'ABC' AND c2>X` - shows all rows that satisfy both conditions of AND operation
21. `SELECT * FROM movies_basic WHERE c1 LIKE 'ABC' OR c2>X` - shows all rows that satisfy any one conditions of OR operation
