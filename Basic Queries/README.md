1. `SHOW DATABASES` - show all databases 
2. `CREATE TABLE mathtest (d1 DECIMAL(4,2), d2 DECIMAL (4,2), f1 FLOAT, f2 FLOAT)` - create a database with name "mathtest" containing 4 columns d1,d2 of decimal values containing max 4 digits with 2 digits after decimal point and f1,f2 float values
3. `INSERT INTO mathtest VALUES (1.5, 1.7,2.5,2.7)` - insert the 4 values into 4 columns d1,d2,f1,f2
4. `SELECT d1+d2 FROM mathtest` - select d1,d2 and add them up to display
5. `CREATE DATABASE dbname` - creates a new database/schema with name dbname
6. `DROP TABLE `schemaname`.`tbname`` - drops the table with name 'tbname' from the schema 'schemaname'
