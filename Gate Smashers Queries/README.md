`1. Create Table`

//last attribute doesn't have comma after it because it has closing bracket followed by semicolon

create table employee

( 

id int, name varchar2(20), salary number(10)

);

`2. Show table`

desc employee;

`3. Alter Table - Add`

alter table employee add address varchar2(10);

`4. Alter Table - Modify Column Data Type`

alter table employee modify address varchar2(30);

`5. Alter Table - Modify Column Name`

alter table employee rename column id to roll_no;

`6. Alter Table - Table Name`

alter table employee rename to emp;

