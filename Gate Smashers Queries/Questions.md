## 1. Write an SQL query to display maximum salary from 'employee' table

select max(salary) from employee;

## 2. Write an SQL query to display the name of employee who has maximum salary from 'employee' table

select name from employee where salary = max(salary);

## 
